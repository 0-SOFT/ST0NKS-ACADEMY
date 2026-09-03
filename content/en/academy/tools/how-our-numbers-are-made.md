---
title: Where our numbers come from
description: Public exchange interfaces, a three-minute collection pass, a freshness marker with three states, and the limits we say out loud
slug: how-our-numbers-are-made
pair: how-our-numbers-are-made
section: tools
date: 2026-09-03
topics: [tools, data, honesty]
---

A tool that shows numbers owes you an account of where they came from. Without one, the reader is
asked to trust — and trust is a poor substitute for checking.

## The source

We collect everything ourselves, through the **public interfaces of the exchanges** — the same ones
open to anyone. No number is taken from another service and no one else's conclusions are
recalculated: another service's shelf is entitled to differ from ours, because our venue coverage and
our spread formula are our own.

Measured 3 September 2026: a pass covers 28 centralised venues and 8 chains for decentralised ones,
gathering on the order of 9,300 quotes.

## Passes, not a stream

Collection runs in **passes**: a sequential sweep of the venues, after which the shelves are
published whole and at once. In the same measurement a pass took **174 seconds**, and that number
explains the interface: the age of the data on the shelf ranges from zero to one pass duration.

Which has a consequence worth knowing: **the shelf shows the state at the end of the last pass, not
"right now"**. The pair page is different — order books arrive there as a stream and prices update
continuously.

## The freshness marker has three states

| State | Meaning |
|---|---|
| data is fresh | the age is within the threshold |
| data is stale | the age exceeded the threshold — collection is late or stopped |
| age is unknown | there is no timestamp: a statement about **our knowledge**, not about the market |

The third state exists because we measured our own untruth. The staleness threshold used to be a
number written once — 100 seconds — while collection passes took between 98 and 170 seconds. Four
observations out of six landed beyond the threshold, so the shelf declared living data stale for most
of every cycle. A warning that lights up in normal operation teaches people to ignore warnings.

The threshold is now **derived from the observed rhythm**: two pass durations, as measured by the
collector itself. With a 174-second pass the threshold is 348 seconds, and both numbers are published
in the response — so the verdict can be checked rather than merely read.

## What we compute ourselves

- **The spread** — from the top of both books, divided by the larger price, less both venues' taker
  fees.
- **The fee** — whatever the venue publishes; where it publishes nothing, 0.05 % per leg is
  substituted, and the article on the spread formula says so.
- **Funding** — normalised to eight hours, because venue intervals differ.
- **The possible-collision flag** — from a leg price that disagrees with the median across all venues.
- **The tradability estimate** — spread or funding gap, multiplied by volume, penalised for a
  suspected collision.

## Limits we state out loud

**24-hour turnover is a poor measure of executability.** We use it in the tradability estimate and we
know it describes yesterday rather than the present book. In the same measurement the top row of the
shelf was a pair showing 22.78 % with one leg on a venue whose book was 2.3 % wide against 0.01 %
elsewhere. The number is right; the trade is not there. It is recorded with us as an open finding,
and executability will be judged from the book.

**Deposit and withdrawal state is what the venue reports, not what we verified.** A venue can keep
withdrawals nominally enabled while requests sit in a queue.

**We do not have deep history for every pair.** Where history is thin, the chart shows few points and
says so, instead of drawing a handsome line out of nothing.

## Why write this down

A list of limits is more useful in a textbook than a list of merits. A tool that reports what it does
not know can be checked; a tool that knows everything can only be believed.

## In short

The numbers are collected by us from public exchange interfaces, a pass takes about three minutes,
the age of the data is shown honestly, and its threshold is derived from a measured rhythm rather
than from a number written once. Everything we are unsure of is named in this article.
