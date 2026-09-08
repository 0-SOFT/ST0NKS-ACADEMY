---
title: DEX–CEX arbitrage and why you hedge
description: One leg on a blockchain, and why the hedge is opened at once, not after the transfer
slug: dex-cex-arbitrage
pair: dex-cex-arbitrage
section: mechanics
date: 2026-09-08
topics: [mechanics, dex]
---

Buying on a decentralized exchange and selling on a centralized one at the same time — or the reverse.
The difference from CEX–CEX is that one venue runs on a blockchain, with its own fees, speed and
contract risk.

## Why you hedge

Buy on a DEX and sell on a CEX is an obvious idea. The problem is the gap in between: while the tokens
move from the DEX to the CEX, the price can run away, and instead of profit you get a loss. The solution
is a hedge: the opposite position on the CEX is opened AT ONCE, not after the transfer.

## The order of steps

1. Open a short on the CEX at the high price.
2. Buy the token on the DEX at the low price.
3. When the CEX futures price converges with the DEX price, close the short and lock in the difference.

## The takeaway

The point of the hedge is to remove price-movement risk while the coin is in transit. Without it,
DEX–CEX is not arbitrage but a bet that the price will not move during the transfer.
