---
title: Reading the scanner table
description: What each column means, what the shelf actually looks like, and why the biggest numbers are the least interesting
slug: how-to-read-the-scanner
pair: how-to-read-the-scanner
section: start
date: 2026-09-03
topics: [basics, scanner, spread]
---

The scanner lists pairs: a token, two venues, a spread, some volumes. The useful way to read it is
one row at a time — but before any single row makes sense, it helps to know how the numbers are
distributed across the whole table.

## What the shelf looks like

Measured on our own shelf, **3 September 2026**: 1,323 pairs collected (the shelf reported 1,348 at
that moment — the data shifts between page requests, which is expected).

| Statistic | Value |
|---|---|
| median spread | **0.348 %** |
| a quarter of pairs sit below | 0.155 % |
| three quarters sit below | 1.278 % |
| pairs below 1 % | **950 of 1,323 — 72 %** |
| pairs above 10 % | 177 (13 %) |
| flagged as possible collisions | 98 |

The first row is the one that matters. **A typical pair pays a third of a percent.** That is what a
market with fast participants looks like: anything conspicuous gets closed, and a thin layer is what
remains.

Which suggests a habit worth forming early: a double-digit number is not "the best opportunity", it
is **a prompt to find out why it is there**. Thirteen percent of the shelf is double-digit, and
almost every one of those has an explanation unrelated to profit — a thin market, a closed
withdrawal, two different coins under one ticker.

## The columns

**Token.** The pair's base asset. The same symbol on two venues does not guarantee the same coin;
there is an article on collisions for that.

**Two venues.** Left is where we buy (the long leg), right is where we sell (the short leg). Any
combination is allowed: spot against perpetual, perpetual against perpetual, spot against spot.

**Spread.** The gap between top-of-book prices, divided by the larger one, less both taker fees.

**Volumes.** Each leg's 24-hour turnover — the most under-read and most misleading column on the
table. Turnover describes **yesterday**; the trade has to fill **from the book as it is now**. A
venue with large turnover and a wide book right now is an entirely ordinary situation.

**Funding.** For perpetual legs, the periodic payment normalised to eight hours so that venues with
different intervals can be compared at all.

## The default sort is not by spread

By default the table is ordered by a tradability estimate: spread multiplied by volume, penalised
when a collision is suspected. The intent is to lift pairs where size can actually be taken above
pairs where the number is merely large.

**Said plainly: it does not fully achieve that.** In the same measurement, the top row of the default
view was a pair showing 22.78 %, on which one venue's book was 2.3 % wide against 0.01 % everywhere
else. The number is correct and the trade is not there. We measured it, wrote it down, and are fixing
it: executability has to be judged from the book, not from yesterday's turnover.

Until then, the rule is simple: **the higher the row, the harder you should look at the book.**

## Reading one row, in order

1. Is the spread double-digit? Find the reason before computing a profit.
2. Do you know both venues? An unfamiliar one is a reason to check withdrawals and depth.
3. Open the pair page: both order books, their depth, the spread's history.
4. Confirm it is one coin: contract address, network, volume.
5. Only then work out what survives fees and the transfer.

## In short

The shelf is a filter, not a list of ready trades. A typical pair pays a third of a percent, and
anything noticeably larger owes you an explanation — which, most of the time, exists.
