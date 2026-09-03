---
title: Where the spread percentage comes from
description: The two prices behind it, the denominator that keeps it sane, and the two fees it already accounts for
slug: how-spread-is-computed
pair: how-spread-is-computed
section: mechanics
date: 2026-09-03
topics: [spread, order book, fees]
---

Every row in the scanner carries a spread in percent. It is not a score and not the output of a
model: it is a subtraction and a division, and you can redo it on paper. Being able to redo it is
the point — that is how you learn what the number leaves out.

## A coin does not have "a price"

It has, on each venue, two prices that matter right now. The **ask** is the cheapest sell order
sitting in the book, and it is what you pay when you buy. The **bid** is the dearest buy order, and
it is what you get when you sell.

A pair takes exactly one price from each venue: the **ask** where it buys, the **bid** where it
sells. Neither is the last traded price, which describes something that has already happened, and
neither is an average.

## The denominator

```
gross % = (bid_where_we_sell − ask_where_we_buy) / bid_where_we_sell × 100
```

We divide by the **higher** of the two prices. The consequence is worth stating: a gross spread can
never reach 100 %. Divide by the lower price instead and a mispriced pair produces something like
"4000 %", which does not describe a trade at all — it describes two different coins sharing one
ticker symbol on two venues.

This does not make the number trustworthy. It only keeps meaningless numbers out of the table.

## Two fees, because there are two trades

```
net % = gross % − fee_on_the_buy % − fee_on_the_sell %
```

This is where intuition usually goes wrong. A gross spread of 0.08 % against a fee of 0.05 % per
side is not "roughly break-even": it is a loss of 0.02 %.

Where a venue publishes its taker fee, we use the published figure. Where it does not, we substitute
**0.05 % per leg** — a conservative taker rate. We say so rather than hiding it: wherever the
substitution applies, the number is slightly approximate, and knowing that is worth more than
looking at a tidy figure.

Taker, not maker, because arbitrage executes against the book immediately. A resting order costs
less in fees and may find the spread gone by the time it fills.

## Worked example

The figures are chosen for the arithmetic, not taken from the market:

| Quantity | Value |
|---|---|
| ask on the buying venue | 100.00 |
| bid on the selling venue | 101.00 |
| gross spread | (101 − 100) / 101 × 100 = **0.99 %** |
| buy-side fee | 0.05 % |
| sell-side fee | 0.05 % |
| net spread | **0.89 %** |

Fees took a ninth of the gross spread here. On a gross spread of 0.15 % they would take two thirds
of it.

## Four things the number does not contain

1. **Depth.** Both prices are top-of-book. Behind them sits a finite size. If the best price holds
   two hundred dollars, the spread applies to two hundred dollars, not to your intended size.
2. **The network fee**, whenever the coin has to move between venues.
3. **Time.** Prices move while the two legs execute.
4. **Whether withdrawal is even open.** A spread between two venues that cannot pass the coin
   between them is a picture, not a trade. Deposits and withdrawals get suspended without notice.

The first of these is visible on the pair page, which shows both order books and their depth. The
rest have articles of their own in this section.

## In short

The spread column is the gap between two top-of-book prices, divided by the larger one, less two
taker fees. Everything capable of making the trade impossible lives **outside** that number — in the
depth of the book, in the state of the networks, and in how fast the two legs actually fill.
