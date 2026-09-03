---
title: The day our collector killed itself
description: The shelf went dark for minutes at a time, and the culprit was not the market but the watchdog restarting the worker five seconds before it published
slug: shelf-went-dark
pair: shelf-went-dark
date: 2026-09-03
topics: [postmortem, data, reliability]
---

On 3 September I was taking a screenshot of the shelf for a textbook article and saw a red "data is
stale" badge. The shelf listed 729 pairs instead of the usual thousand-plus. An hour of digging
turned up a fault that had been hiding behind an apparently healthy system for weeks.

## What it looked like from outside

Nothing had been published to the bus for **eleven minutes**. Meanwhile the collector's log showed
passes **completing**:

```
16:26:09  pass: quotes=9301 spreads=1473 funding=1109
16:29:31  pass: quotes=9303 spreads=1475 funding=1109
```

Data was being gathered. Data was not being published. A third line — "Redis: spreads=…" — belongs
between those two, and it was missing.

## What the watchdog log said

```
16:26:04  Container ingestion found to be unhealthy - Restarting container
16:29:36  Container ingestion found to be unhealthy - Restarting container
```

**The container was being restarted five seconds before it published.** Every time.

## Why the liveness check believed the worker was dead

The collector has a check: if the last successful pass was long ago, the loop has hung and the
container should be restarted. That is a sensible guard — without it, a hung collector would quietly
serve yesterday's prices.

The trouble is in the numbers. The first pass after a start takes **175 seconds**: it has to load
market metadata for twenty-eight venues and then walk all of them. The application, however,
considered itself healthy for only 120 seconds after start, and demanded a completed pass thereafter.

From there the loop closes on itself:

1. the pass does not finish inside the allowance;
2. the watchdog restarts the container;
3. after a restart the metadata cache is empty, so the next pass takes **even longer**;
4. return to step 1.

You leave a loop like that by luck — when some pass happens to fit.

## What we changed

**First, to stop the bleeding.** The liveness check now gets five minutes for the first pass. That
applies without a rebuild and takes a minute.

**Second, the substance.** Liveness stopped meaning "a pass finished" and started meaning "the loop
is turning": the collector records progress on **every venue that returns data**. A three-minute pass
no longer looks like death, while real death is still visible — if no venue has returned data for
longer than the threshold, the loop genuinely is not turning.

One detail that is easy to lose: progress is recorded only where **data exists**. Recording the mere
attempt would hand the best possible liveness score to a pipeline where every venue fails instantly —
it would "progress" faster than anything healthy.

**Third.** It turned out the loop could stall for another reason entirely: the decentralised-market
step waited out the source's rate limits and held the next pass for **six minutes**. That step is now
capped at the duration of the last ordinary pass — over budget means dropped until next time. The
shelf matters more than coverage.

## Before and after

| | before | after |
|---|---|---|
| worker restarts per half hour | 2 in 4 minutes | **0 in 30 minutes** |
| publications per half hour | an 11-minute gap | **15** |

## What it teaches

A guard configured by a number nobody rechecked is worse than no guard: it looks like care and does
harm. The numbers 120 and 175 lived in different files and never met — until they met in production.

And the second lesson: **a liveness check has to answer the question it was written for.** The
question was "is the loop turning"; what it actually asked was "did a pass finish". Those are
different questions, and the difference cost us minutes of an empty shelf.
