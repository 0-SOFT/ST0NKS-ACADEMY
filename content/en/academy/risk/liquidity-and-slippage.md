---
title: Liquidity and slippage
description: The spread belongs to the size resting in the book, not to the size you had in mind
slug: liquidity-and-slippage
pair: liquidity-and-slippage
section: risk
date: 2026-09-03
topics: [risk, liquidity, order book]
---

A spread is computed from the top of two order books. The top of a book is a price **and a size**,
and the size is the half nobody reads. Between "the spread is 5 %" and "I made 5 %" sits one
question: five percent of how much?

## A book is a staircase

Orders rest at many prices. Your buy consumes them in order, cheapest first. While the top level has
size left, you pay the top-level price; once it is exhausted, the fill continues at the next level,
which is worse.

The gap between the price you saw and the average price you actually got is **slippage**. It is
neither an error nor a trick: it follows directly from taking more than the best price held.

Two consequences, both boring until the first time:

- **the larger the order, the worse its average price;**
- in arbitrage, slippage is paid **twice** — once on each leg.

## Book width as a measurement

Liquidity has one simple observable: the **inside spread** of a book, the gap between its best bid
and best ask on a single venue. Measured 3 September 2026, ZEC:

| Venue | Best bid | Best ask | Inside spread |
|---|---|---|---|
| Binance | 940.00 | 940.08 | **0.01 %** |
| Poloniex | 710.76 | 727.35 | **2.3 %** |

A factor of two hundred. On the first venue, buying and immediately selling costs a hundredth of a
percent. On the second it costs over two percent — before you take any size at all.

A wide book almost always means little size behind the top level. So a pair with one leg on such a
venue displays a large spread and will not hand it over: the attempt to execute moves the price to
where the spread no longer exists.

## Turnover does not answer this

It is tempting to judge liquidity by 24-hour turnover, because turnover is always in the table. But
turnover describes **yesterday**, and the fill happens **now**. In the same measurement, the venue
with the 2.3 %-wide book reported 46 million dollars of turnover.

Turnover and depth answer different questions — "how much traded here" versus "how much is sitting
here". Only the second one is about your trade.

## Sizing it honestly

1. Open both legs' order books on the pair page.
2. Read the **cumulative size** available within a price you would accept — across the first few
   levels, not just the best one.
3. Take the **minimum** of the two legs: the trade is capped by the thinner side.
4. Reduce your size to that, or drop the pair.

Our pair page shows both books and computes the executable size. Where the book covers less than you
asked for, the numbers are shown for the **executable** portion rather than the requested one.
Quoting a price for size that is not there is the easiest way for an interface to lie.

## In short

The spread is a property of the top of the book. Your profit is a property of its **depth**. They are
different quantities, and the second is always the smaller one.
