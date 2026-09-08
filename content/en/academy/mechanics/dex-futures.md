---
title: Arbitrage between a DEX and futures
description: A DEX–CEX variant that works in one direction only
slug: dex-futures
pair: dex-futures
section: mechanics
date: 2026-09-08
topics: [mechanics, dex]
---

A variant of DEX–CEX where the centralized side is a futures market. It works with various venues, but
the strategy has a hard limit.

## One direction only

The pair is possible only when the DEX price is LOWER than the CEX price. Then the asset is bought on the
DEX and a short is opened on CEX futures — the difference is locked. The reverse order is physically
impossible: opening a long on futures does not give you the asset in hand, so you cannot sell it on the
DEX.

## What you need

- two venues — a DEX and a CEX;
- buy on the DEX, short on the CEX;
- the DEX price below the CEX price;
- money must sit on BOTH venues — without that the pair cannot be assembled.

## The takeaway

The asymmetry here is not a service limitation but a property of futures: they do not hand you the coin.
So only the "buy on the DEX, hedge with a short" direction works.
