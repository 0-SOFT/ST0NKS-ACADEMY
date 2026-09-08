---
title: Rugs and depegs: when a huge spread is a trap
description: Two sudden moves where a pair stops existing faster than you can close it
slug: rugs-and-depegs
pair: rugs-and-depegs
section: risk
date: 2026-09-08
topics: [risk, stablecoins]
---

There are two kinds of sudden move where a huge spread means "stay out," not "get in": a token rug and
a stablecoin depeg. In both, the pair stops existing faster than it can be closed.

## Why this is a risk, not an opportunity

A rug and a depeg both look like an arbitrageur's dream: the price split hard, the spread is enormous.
The difference from a working pair is WHAT IS BEHIND the divergence.

| | Organic spread | Rug or depeg |
|---|---|---|
| Cause | market: funding, liquidity gap | the asset loses value or its peg |
| Dynamics | converges | may never converge |
| Exit liquidity | present | vanishes with the price |

An organic spread converges because a market reason holds it. A rug has a different cause — the asset
simply lost value, and it has nothing to converge back to.

## A rug: minus most of the value in five minutes

A rug is a token collapsing by tens of percent in minutes, up to near-total wipeout. The visible spread
at that moment is the gap between an already-dead price on one venue and a not-yet-updated one on
another. The practical meaning is double: don't enter on such a token, and check whether it is already
in one of your open pairs. Telling a specific coin's rug from a mere ticker match is what the contract
address is for, not the name alone.

## A stablecoin depeg

A stablecoin is built to trade near its peg. A deviation — a depeg — means the market doubts the
promised dollar still stands behind it. The spread between a "broken" stable and a normal one looks like
free money, but you would be buying something that may never return to its peg, while exit liquidity
disappears ahead of you.

## The takeaway

A spread says nothing until you know WHY it is there. If the price split because an asset lost its value
or its peg, it is under no obligation to converge — and a huge number turns out to be not profit but the
speed at which you fall into it.
