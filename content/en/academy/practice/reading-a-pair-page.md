---
title: The pair page, in the order that matters
description: Five checks that separate an executable pair from a pretty number
slug: reading-a-pair-page
pair: reading-a-pair-page
section: practice
date: 2026-09-03
topics: [practice, pair, order book]
---

The shelf exists to shortlist. The decision happens on the pair page, where you can see what a table
cannot show: both order books, the spread's history, and the specific reasons a trade will not
happen.

The order below is not a tour of the interface. It is the sequence that rejects fastest — each step
costs more than the one before it, so the cheap questions go first.

## 1. Is it one coin?

Look at the two leg prices. A difference in multiples is almost certainly **two different coins
sharing a ticker**; a difference in percent is a working situation. If the pair carries a possible-
collision flag, compare the contract address on both venues — different addresses end the discussion.

This is the cheapest question and it rejects the most tempting numbers. Ask it first.

## 2. Is the data alive?

The page carries a freshness marker with **three** states, not two: data is fresh, data is stale, or
the age of the data is unknown. The third is a statement about our knowledge rather than about the
market, and we say it out loud instead of painting everything red.

Check the legs separately — each has its own marker. One leg can stop updating while the other is
perfectly alive, and then the spread between them is computed from an old price and means nothing.

## 3. What is actually in the books?

Both books are shown with their depth. What you are checking here is not price but **size**: how
much can be taken without walking far from the top.

In practice: take the size you have in mind and see whether the **thinner** leg's book covers it. Our
page computes the executable size itself — where the book covers less than requested, the figures
are shown for the executable part, which is more honest than showing the wish.

A wide book — best bid and best ask far apart — tells you there is little size behind the top level,
and that trying to execute will move the price.

## 4. How does the spread behave over time?

The spread chart answers a question a table cannot be asked: is this a one-off print or a persistent
state?

- **A narrow band with occasional spikes** — an ordinary pair; the spikes are closed by fast
  participants.
- **A persistently wide spread over many hours** — a signal that nobody is closing it. There is
  usually a reason: withdrawals suspended, a thin market, restricted access. Find the reason before
  the trade rather than after.
- **No history** — the pair is new or the data is sparse. Then the decision rests on the current book,
  not on the past.

## 5. Deposits, withdrawals, network

The last check is the dullest and the most decisive: can the coin move between these two venues at
all, and on which chain? A spread between venues with no shared network is not a trade.

## Summary

| Step | Question | Where to look |
|---|---|---|
| 1 | is it one coin | leg prices, contract address |
| 2 | is the data alive | freshness marker, per-leg markers |
| 3 | how much can be taken | both books and their depth |
| 4 | is the spread persistent | the spread chart |
| 5 | is a transfer possible | deposit/withdrawal state, network |

## In short

The pair page exists to **disprove** an opportunity, not to confirm one. A pair that survives all
five checks has earned its arithmetic; one that fails the first has saved you an afternoon.
