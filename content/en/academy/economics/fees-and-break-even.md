---
title: Fees and the break-even threshold
description: How much spread a trade needs before it means anything — and what that looks like on a real shelf
slug: fees-and-break-even
pair: fees-and-break-even
section: economics
date: 2026-09-03
topics: [economics, fees, break-even]
---

Every pair has a number below which it loses money no matter how well it is executed. It is the
break-even threshold, it takes a minute to compute, and it removes most of the table.

## What the threshold is made of

```
threshold = buy-side fee + sell-side fee + network fee (as % of size) + a margin for slippage
```

The first two scale with size. The third is a fixed amount. The fourth depends on your size and on
the depth of the books.

A typical taker fee is **0.05 % per leg**, or 0.10 % for the round trip. That is the figure we
substitute when a venue does not publish its own; where it does, we use theirs.

## What that means on a real shelf

Measured on our shelf, **3 September 2026**, 1,323 pairs:

| Statistic | Value | Left after 0.10 % of fees |
|---|---|---|
| a quarter of pairs below | 0.155 % | 0.055 % |
| median | 0.348 % | **0.248 %** |
| three quarters below | 1.278 % | 1.178 % |

Read it like this: **fees consume nearly two thirds of the spread across the bottom quarter of the
shelf**, and about a third of the median pair. None of these pairs is "bad" — they simply require
either size or a structure with no transfer in it.

And a threshold made of venue fees alone is the mildest one available. The network is not in it yet.

## The network fee breaks the proportion

A network fee is a fixed amount, so as a percentage it depends only on how much you move. Take a
one-dollar fee against the median spread of 0.348 %:

| Transfer size | Network fee as % | Median spread less fees |
|---|---|---|
| 100 | 1 % | **−0.75 %** (a loss) |
| 1,000 | 0.1 % | 0.148 % |
| 5,000 | 0.02 % | 0.228 % |
| 50,000 | 0.002 % | 0.246 % |

The identical number in the spread column is a loss on a hundred dollars and a profit on five
thousand. Hence the practical point: **the break-even threshold takes an argument, and the argument
is size.** Asking whether a pair is worth trading, without a size, has no answer.

## Why the slippage margin is not a luxury

Fees are known in advance; slippage is not. It depends on what rests in the book at the moment of
execution, not at the moment you looked at the table. A sane order of work: compute the threshold
without slippage first, then read the depth and decide whether your size fits.

If only a quarter of it fits, that is not a prohibition. It is a different trade — smaller, with the
same arithmetic.

## Funding, briefly

When one leg is a perpetual contract, funding joins the arithmetic: a periodic payment that can add
to the result or subtract from it. For a trade that lives for minutes it is negligible. For a
position held for a day it is not.

## In short

Break-even is the first thing to compute, and it is always computed **together with a size**. The
median pair on our shelf pays 0.348 %; venue fees take 0.10 % of that, and the network fee takes
anywhere from nothing to all of the rest — depending on nothing but how much you move.
