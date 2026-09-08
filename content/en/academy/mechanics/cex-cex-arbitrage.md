---
title: CEX–CEX arbitrage
description: The simplest kind: a price gap of one asset across two centralized exchanges
slug: cex-cex-arbitrage
pair: cex-cex-arbitrage
section: mechanics
date: 2026-09-08
topics: [mechanics, cex]
---

The simplest kind of arbitrage: the same asset trades at different prices on two centralized exchanges;
you buy where it is cheaper and sell where it is dearer.

## Where the spread comes from

- different liquidity across venues;
- different supply and demand on a specific exchange;
- deposit and withdrawal limits — the asset is "locked" and cannot go where it is dearer;
- an error by the exchange itself.

The last two matter more than they seem: a spread from a closed withdrawal looks more attractive than
the rest precisely because no one can close it by transferring coins — and for the same reason it is
more dangerous.

## Two forms: spot and futures

On spot you buy the coin itself and sell it on another venue — a withdrawal is needed. On futures you
open a long on the cheap exchange and a short on the dear one, and profit comes from convergence,
without moving the coin.

## The takeaway

The simplicity of CEX–CEX is deceptive: the largest spread is most often the one that cannot be closed.
Before entering, check that withdrawal is open and the order book is alive.
