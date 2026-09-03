---
title: What cross-exchange arbitrage is
description: One coin, two venues, two prices — and why that is not free money
slug: what-is-arbitrage
pair: what-is-arbitrage
section: start
date: 2026-09-03
topics: [basics, spread]
---

Cross-exchange arbitrage means buying an asset where it is cheaper and selling it, at the same
time, where it is dearer. Described that way it sounds like free money. In practice the whole
difficulty hides in the words "at the same time", and in the fact that every action costs money.

## Where the price difference comes from

A price on an exchange is not a property of the coin. It is the outcome of trading ON THAT VENUE.
Different venues have different participants, different demand, and different deposit and
withdrawal rules. So differences appear constantly — and constantly disappear, closed by whoever
saw them first.

The difference, expressed as a percentage, is called the **spread**. A 2 % spread means the coin
costs two percent more on one venue than on the other. That is not profit yet. It is the raw
material that profit still has to be subtracted from.

## Why a spread is not profit

Between the spread you see and the money in your account stand five things, each of which makes
it smaller:

1. The **buy fee** on the first venue.
2. The **sell fee** on the second.
3. **Slippage**: only a limited size sits at the best price, so a large order fills worse than the
   top line of the book suggested.
4. The **network fee** for moving the coin between venues, when a move is needed at all.
5. **Time**: while the trade is being placed the price moves, and the spread may close before you
   are done.

The sum of the first four is the threshold below which a trade loses money even when everything
else goes perfectly. That has an article of its own.

## What the scanner shows

Our scanner computes the spread from the TOP OF THE ORDER BOOK on both venues: the buy price where
we would buy, against the sell price where we would sell. It is the most honest of the simple
methods — it never promises more than the book shows right now.

On the pair page the order book of both legs is shown next to the spread, together with its depth.
If two hundred dollars sit at the best price, a 5 % spread applies to those two hundred dollars,
not to your deposit.

## The point

Arbitrage is not the search for a large number in a table. It is the check of whether anything is
left of that number once everything listed above has been subtracted from it.
