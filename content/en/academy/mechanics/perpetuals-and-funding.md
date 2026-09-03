---
title: Perpetuals and funding
description: A position has a cost of carry — and the difference in that cost between venues is itself a trade
slug: perpetuals-and-funding
pair: perpetuals-and-funding
section: mechanics
date: 2026-09-03
topics: [funding, perpetuals, mechanics]
---

A perpetual contract is a future with no expiry date. You can hold it indefinitely, which is exactly
why it needs a mechanism to keep its price tied to spot: **funding**.

## How the tether works

An ordinary future has a date, and its price converges to spot on its own by that date. A perpetual
has no date, so convergence is bought with money: at fixed intervals, holders of one side pay
holders of the other.

- The contract trades **above** spot: longs pay shorts.
- The contract trades **below** spot: shorts pay longs.

The payment realigns incentives — holding the overpriced side becomes expensive, and the price is
pulled back.

The rate is not a forecast and not the venue's opinion. It is a consequence of which side currently
has more demand.

## Intervals differ between venues

Some venues settle every eight hours, some every four, some hourly. Raw rates therefore cannot be
compared: 0.01 % every hour and 0.01 % every eight hours differ by a factor of eight.

We normalise every rate to **eight hours** before comparing anything. It is the only way to put
several venues in one table without lying.

## Funding as a trade in its own right

When the same contract carries different rates on two venues, you can hold the long where you are
paid and the short where you pay less. The prices stay tied together, market direction barely
concerns you, and the income comes from the **difference in rates**.

Measured on our funding shelf, **3 September 2026**: 1,109 tokens, each with two or more perpetual
legs. The gap between a token's highest and lowest daily rate:

| Statistic | Value |
|---|---|
| median | **0.032 % per day** |
| three quarters of tokens below | 0.122 % per day |
| 95 % of tokens below | 0.457 % per day |
| maximum | 6.51 % per day |
| tokens with a gap above 0.1 % per day | **29 %** |
| tokens with a gap above 1 % per day | 2 % |

The median is modest — three hundredths of a percent a day. But the distribution has a long tail:
nearly a third of tokens exceed a tenth of a percent per day, which is already comparable to the
median spread across the entire pairs shelf (0.348 %) — except that it recurs every day the position
stays open, instead of being collected once.

## What you pay for it

1. **The rate moves.** It is recalculated every interval, and yesterday's gap promises nothing about
   tomorrow's.
2. **Collateral on two venues.** A sharp price move can demand a top-up on one side while the profit
   on the other side is still unrealised.
3. **Liquidation.** A leveraged position gets closed for you, and being delta-neutral does not
   prevent it: each leg is liquidated under its own venue's rules.
4. **Entry and exit fees** are paid immediately, while funding arrives in instalments — a short-lived
   position may never earn them back.

## Reading it in our table

The funding column shows the rate normalised to eight hours. For a pair, we show the difference
between the legs. The sign matters: it says who pays whom, and without it the number means nothing.

The tradability estimate behind the default sort uses the **better of the two** — spread or funding
gap — because a pair can be worth attention with no spread at all.

## In short

Funding is the cost of holding a position. It can be negative, in which case holding pays you. For
the median token the gap between venues is small, but for a third of tokens it is visible and it
repeats daily — unlike a spread, which is collected once.
