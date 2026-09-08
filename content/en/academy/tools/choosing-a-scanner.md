---
title: The scanner market: how to choose
description: The categories of tools, what to look at, and where ST0NKS sits among them
slug: choosing-a-scanner
pair: choosing-a-scanner
section: tools
date: 2026-09-08
topics: [tools, choosing]
---

There are many scanners, and they differ not in "quality" in general but in what exactly they do. Let us look at the categories and the criteria to compare them by.

## Three categories

| Category | What it does |
|---|---|
| Specialized scanners | monitoring only: they show price gaps, they do not trade |
| Trading platforms | arbitrage is one feature among many, with auto-trading |
| Built-in exchange bots | they work inside a single venue |

## What to look at

**Whether fees are accounted for.** A scanner showing a gross spread without deducting costs shows non-existent profit. This is the main criterion — see the economics section.

**Whether an API key is needed.** Connecting a scanner to an exchange by API key transfers to it part of the trust you place in the exchange. A tool that only reads or works through notifications does not create that risk. There are known cases where a trading platform's API-key leak cost users six-figure sums.

**Ticker confusion.** Coins with the same ticker on different exchanges can be different assets; a scanner that confuses them shows phantom pairs.

## Open-source: only a few alive

Of dozens of open-source arbitrage projects, only a handful remain in active development by 2026. Most went through one cycle: development in a bull market, then abandonment. An independent review of 50-plus open bots found 70% do not work, 25% are instantly unprofitable, and only about 1% are potentially profitable.

## Where ST0NKS sits

ST0NKS is a free showcase and analytics with no auto-trading. We do not ask for API keys to your exchanges — so we do not create the risk described above. We compute the spread ourselves and honestly flag when data is stale or a pair's leg is incomplete. Our value is not "the largest coverage" but verifiability: the number you see is backed by a chart and a liveness marker.
