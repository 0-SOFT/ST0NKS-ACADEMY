---
title: "Case study: a loss while the price stood still"
description: How the fill price ends up worse than the screen price, even when the market does not move
slug: case-orderbook-slippage
pair: case-orderbook-slippage
section: practice
date: 2026-09-08
topics: [practice, order book]
---

The most underrated source of a beginner's losses does not look like a loss. It looks like "about what
it should be."

## The experiment

On a pair with a noticeably thin order book, a position of just $19 is opened and immediately closed.
The asset's price did not move in that time — yet the position still closed at a loss of about **0.07%**
on the open-and-close round trip.

## Why it happens

The price the exchange shows in large type is a reference. The trade fills FROM THE ORDER BOOK, against
quotes: you buy at the best ask, sell at the best bid, and between them there is always a gap. On a
liquid pair that gap is tiny; on a thin one it is real, and you pay it twice: on the way in and on the
way out.

## What follows

The spread in the table is computed from the top of each book, but only a LIMITED size sits at the best
price. A 5% spread applies only to the dollars on that top line, not to your whole deposit. That is why
the pair page shows book depth next to the spread — so the number does not promise more than is there.

## The takeaway

The screen price is an intention, the order-book price is a fact. On a thin pair you can end up in the
red without a single price move — simply by paying to enter and exit.
