---
title: Funding arbitrage
description: Earning on the funding rate rather than price — and how not to confuse the sign
slug: funding-arbitrage
pair: funding-arbitrage
section: mechanics
date: 2026-09-08
topics: [mechanics, funding]
---

Earning not on the asset's price but on the funding rate — a periodic payment between longs and shorts
on the futures market. Open opposite positions on two exchanges, and price movement stops affecting the
result while the difference in rates remains.

## Reading the sign of the rate

| Rate | Who pays whom | If long | If short |
|---|---|---|---|
| Positive | longs pay shorts | you pay | you receive |
| Negative | shorts pay longs | you receive | you pay |

The rate accrues periodically — on most exchanges every 8 hours, three times a day; on some venues the
period differs.

## The idea of the strategy

Open a long where funding pays your way, and a short where it also pays you or at least does not take
more. The asset's price is cancelled by the two legs, and you live on the difference in rates. The main
risk is an exchange that changes the rate with the skew — then the profit becomes incomputable.

## The takeaway

Funding arbitrage turns the rate into income and price into noise you are shielded from by two legs.
Sort out the sign first — that is where most mistakes are.
