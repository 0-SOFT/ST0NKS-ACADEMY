---
title: Cross-network arbitrage
description: One coin across networks — and why the key is the bridge, not the spread
slug: cross-network-arbitrage
pair: cross-network-arbitrage
section: mechanics
date: 2026-09-08
topics: [mechanics, cross-network]
---

The same coin in different blockchain networks can trade at different prices: buy cheaper in one, move
it across a bridge, sell dearer in another.

## How it differs from the rest

| | Ordinary arbitrage | Cross-network |
|---|---|---|
| Key constraint | liquidity and limits | the existence of a bridge |
| Execution time | seconds to minutes | minutes to hours |
| Main risk | spread convergence | being unable to move the coin |

Here the existence of a route is not a detail of execution but a condition of the trade. The spread can
be anything; if there is no bridge, there is no trade.

## What to check BEFORE entering

1. Is there a bridge between the needed networks, and does it work right now.
2. How much gas costs and how long the transfer takes — the spread can close in that time.
3. Whether the coin's withdrawal is closed on one of the sides.

## The takeaway

A cross-network spread is the one where you check not the number first but the physical ability to move
the coin. No bridge — and the spread stays a picture.
