---
title: Silence is not a refusal
description: We started showing deposit and withdrawal status — and within the hour saw our own data claiming BTC withdrawals were closed on Coinbase and Kraken
slug: silence-is-not-a-refusal
pair: silence-is-not-a-refusal
date: 2026-09-03
topics: [postmortem, data, honesty]
---

A spread between two venues means something only if the coin can move between them. We had been
collecting deposit and withdrawal status for a long time — thousands of venue-and-coin pairs, some
four megabytes of it in the bus. And we had never displayed any of it: the shelf row carried a
hard-coded "unknown" in that place.

On 3 September we fixed that. Within the hour we found out why it should not have been displayed.

## What the first measurement showed

| What our data claimed | The truth |
|---|---|
| BTC withdrawals closed on Coinbase | no |
| BTC withdrawals closed on Kraken | no |
| withdrawals closed for **all 5,071** coins on LAToken | no |
| withdrawals closed for **all 1,134** coins on Phemex | no |

Across the whole set of 37,223 records, "withdrawals closed" was set on **55 %** of them.

## Where the untruth came from

The function reading the flags out of our exchange-access library worked like this: take the flag on
the currency; if it is absent, look at the per-network flags; if there is nothing there either,
**return "not allowed"**.

Its docstring said "this is the honest reading".

It was not. A venue that does not publish the flag at all is not saying "no" — it is **saying
nothing**. Our silence was being presented as its refusal.

## Why the fault lived unnoticed

Precisely because the data went nowhere. The field in the shelf row was a constant, the interface
never drew it, no human ever saw it. The defect was harmless right up to the day it became useful.

That is an uncomfortable regularity: **untruth in data nobody reads has no symptoms**. It waits for
the day the data is finally shown, and then arrives all at once.

## How it works now

There are three answers: "yes", "no", and **"the venue did not say"**. The order of resolution is
written into the code: the currency-level flag; failing that, the networks — one open network makes
the coin open; failing that, if any network said "no", then no; otherwise nothing is known, and we
say so out loud.

In the interface, the "transfer closed" mark appears **only on an explicit refusal from the venue**.
Not knowing is marked with nothing at all: we have no right to turn our own silence into a warning.

## The cost of the two errors is not symmetric

This is worth pausing on, because it is the heart of the matter.

If we stay silent where withdrawals really are closed, the user checks for themselves and loses a
minute. If we **say "closed" where everything is open**, the user abandons a viable trade and never
learns of it.

Between two errors you choose the cheaper one. Our old code chose the expensive one and called it
honesty.

## What turned up along the way

The very pair that started all this: ZEC on Poloniex trades 24 % below the thirty-two other venues
quoting it. The reason was sitting in our own unused data: **ZEC withdrawals from Poloniex are
closed**. Nobody closes the gap because nobody can take the coin out.
