---
title: MEV bots and sandwich attacks
description: Why a DEX trade can fill worse than the screen showed, and who profits from it
slug: mev-bots
pair: mev-bots
section: risk
date: 2026-09-08
topics: [risk, dex]
---

MEV (maximal extractable value) is profit you can extract by controlling the ORDER of transactions in a
block. Legally it isn't fraud: bots use how the blockchain works, they don't lie. But the bill is paid
by whoever simply makes an ordinary DEX trade and gets a worse price than the one shown.

## Where the opening comes from

A validator earns more by arranging transactions well, and a slot in a block is for sale: whichever
transaction bids more gas gets in earlier. So execution order is a contest, and dedicated bots pay to
win it. Ethereum has the most of this; cheap-gas chains such as BNB Smart Chain followed.

## Three mechanics, from harmless to costly

**Arbitrage between DEXes.** The one case where nobody is hurt: a bot sees a token cheaper on one venue
than another and levels the price by buying there and selling here. It is exactly what an honest
arbitrageur does, only faster.

**Front running.** A bot spots a large incoming order that is about to move the price and places its own
trade AHEAD of it by paying more gas. It buys at the old price and sells at the new one the other order
creates.

**Sandwich attack — the most common and the most expensive for the victim.** Three transactions wrap
yours: the bot buys before you (price rises), you execute with heavy SLIPPAGE, the bot sells right
after and takes the difference. You pay both an inflated price and the fees, on both sides.

## How not to feed the bots

- Set a sane slippage limit: a wide tolerance is an invitation to a sandwich.
- Split a large trade rather than sending it in one lump into a thin pool.
- Remember that the price in a DEX interface is an intention, not a guarantee: a lot happens between
  the click and the block.

## The takeaway

MEV is not a bug but a property of open blockchains: transaction order costs money, and someone pays for
it. In arbitrage it hits the DEX leg: the price you planned around and the price you fill at are
different things, and a bot sometimes takes the gap instead of you.
