---
title: What the shelf actually looks like: 1,323 pairs in numbers
description: A median of 0.348 %, three quarters below 1.3 % — and why the first screen showed something else entirely
slug: what-the-shelf-really-looks-like
pair: what-the-shelf-really-looks-like
date: 2026-09-03
topics: [measurement, shelf, spread]
---

We rarely publish internal measurements. This one is worth publishing, because it explains why the
first screen of an arbitrage scanner usually lies — and not only ours.

## The whole shelf

Measured **3 September 2026**: 1,323 pairs collected (the shelf reported 1,348 at that moment — the
data shifts between page requests).

| Statistic | Value |
|---|---|
| median spread | **0.348 %** |
| a quarter of pairs below | 0.155 % |
| three quarters below | 1.278 % |
| pairs below 1 % | **950 of 1,323 — 72 %** |
| pairs above 10 % | 177 (13 %) |

**A typical pair pays a third of a percent.** That is what a market with fast participants looks
like: anything conspicuous gets closed, and a thin layer is what remains.

## Now the first screen

Same day, same shelf, the first ten rows of the default sort:

```
median spread of the first ten:  20.05 %
double-digit spreads:            7 of 10
top row:                         ZEC, 25.35 %
```

**The first screen's median was fifty-seven times the shelf's median.** Not luck, not an unusual day
— a consequence of how "tradability" was computed: spread multiplied by 24-hour turnover. Turnover
describes yesterday; executable size describes the book right now. The first outweighed the second
even when it directly contradicted it.

The top row was the example. ZEC on Poloniex: a 25 % spread, 46 million of turnover — and an inside
book spread of **2.3 %** against 0.01 % on Binance. There is almost nothing behind the top of that
book, and withdrawals of the coin from that venue are closed on top of it.

## What we changed

We now flag a leg whose price has parted company with the consensus of its own venues, and **exclude
its spread** from the tradability estimate. Not penalise it by a factor — exclude it: if the price is
in dispute, the spread computed from it does not answer the question "how much can be taken here".

The measure is relative to how tightly the venues agree, rather than a fixed multiple. That matters:
thirty-five venues quote ZEC within 0.06 % of each other, while a thin token's four quotes scatter
across 5 % — the same percentage deviation means opposite things in those two cases.

## After

| | before | after |
|---|---|---|
| top row | ZEC, 25.35 % | TON, 19.89 % |
| median spread of the first ten | **20.05 %** | **6.97 %** |
| double-digit spreads | 7 | 5 |

Flagged pairs did not disappear: they are findable by search, visible when sorting by spread, and
carry a mark with an explanation. The number is correct — hiding it would be lying in the other
direction.

## What remains honestly unsolved

The double-digit spreads that are left belong to tokens where **price has nothing to say**: two to
four quotes scattered across percents. There is no median, no consensus, and our measure stays silent
rather than guessing.

The answer for those comes from a different measure — from the order book rather than the price:
"how much can be taken" instead of "do the venues agree". We collect books for 136 pairs out of some
1,350, so that is separate work, and we have not done it.
