---
title: Exchange-side risks
description: Losses no hedge protects against, because the venue itself changes the rules
slug: exchange-risks
pair: exchange-risks
section: risk
date: 2026-09-08
topics: [risk, exchanges]
---

The market is not the only thing that breaks a pair. There is a separate class of losses where every
number was right and the money still vanished, because the EXCHANGE changed the terms unilaterally. A
hedge does not protect you here: both legs sit on venues, and either one can change the very thing the
trade was built on.

## A broken market maker

The order book on an exchange is held up by its own bot. It can stall: the price freezes, funding stops
accruing, liquidity is gone. The most dangerous move here is the seemingly CORRECT one — cutting the
loss. Exiting against a dead book is often classified by the venue as market manipulation, and the
account is frozen. Signs: the price does not move, funding stopped, withdrawals are limited. The only
move then is to not exit and to contact support, rather than trade against a dead book.

## A funding rate that shifts under you

Some venues move the funding rate with the skew of retail open interest. When one signal is seen by a
few hundred people who all enter the same side, the skew grows — and the exchange changes the rate. The
consequence matters more than the fact: **the profit of such a pair cannot be computed**. Not "risky"
but literally incomputable — the very quantity you open the position for changes in response to your
opening it. The plain conclusion: avoid funding pairs on such venues.

## Closed deposits and withdrawals

If an exchange closes operations on a coin, arbitrageurs cannot move the spot price. And if the venue's
index price is built from spot, convergence becomes impossible — the spread grows without bound and
never closes. It looks like a giant opportunity; it is a trap with no exit.

## The takeaway

These risks share one thing: the source is not the market but a venue's decision, and a hedge is
powerless against them. Before celebrating a large spread, ask whether it rests on the exchange having
BROKEN or CLOSED something — then it is not a pair, it is a snare.
