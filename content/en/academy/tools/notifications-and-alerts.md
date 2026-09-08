---
title: Notifications and alerts
description: How to set up pair notifications and why a hold time matters
slug: notifications-and-alerts
pair: notifications-and-alerts
section: tools
date: 2026-09-08
topics: [tools, alerts]
---

An alert is a condition that fires on a specific pair and sends you a notification. In ST0NKS alerts are personal: you set the condition and it works only for you.

## Two condition types

| Type | What it fires on |
|---|---|
| By spread | when a pair's spread reaches the set value |
| By price | when a leg's price (long or short) reaches a level — handy for stop-losses and take-profits |

## Why the hold time (Min Hold) matters

A spread flickers and vanishes. Without a hold, an alert will send signals you can no longer act on. The hold is the time a condition must persist before sending. For example: a 1% spread must hold for 15 seconds — only then does the notification arrive. The hold filters out what does not last long enough to become a trade.

## Three kinds of spread — a subtle but real distinction

| Kind | What it means |
|---|---|
| Rate spread | a price difference |
| Funding spread | a rate difference at equal accrual intervals |
| Total spread | a rate difference at different intervals |

The distinction is not a formality: at different intervals, rates cannot be compared directly — 1% every 8 hours and 1% every hour are different quantities. The mechanics are in the funding-arbitrage article.

## Favorites

A pair can be saved to favorites for quick access — the card shows the current spread, exchanges, prices, volumes and funding. An alert is convenient to attach to such a pair so you need not watch it by hand.
