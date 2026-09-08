---
title: "Case study: a broken market maker, when doing nothing was right"
description: The most expensive case: those who tried to cut the loss lost their accounts entirely
slug: case-broken-market-maker
pair: case-broken-market-maker
section: practice
date: 2026-09-08
topics: [practice, risk]
---

The most expensive of the cases studied — and the only one where the right move was to do nothing.

## What happened

The pair: long on one exchange, short on another. During a sharp rise in the coin, the market-maker bot
on the exchange holding the long leg broke.

| | It became |
|---|---|
| Price in the broken book | frozen at ~$12 |
| Price on the second exchange | reached $20–21 |
| The spread | 50–100% |
| Funding | stopped accruing |

At the same time the exchange limited withdrawals for everyone holding positions. Two people who tried
to cut the loss against a dead book lost their accounts entirely: the exit was classified as
manipulation.

## Why waiting was right

An astronomical loss on the screen is a paper figure computed against a dead book. While the book does
not work, you cannot close at a sane price, and an attempt to exit at any price is a gift to an exchange
that has already limited withdrawals. Waiting for the book to recover is the only chance to bring the
legs back to reality.

## The takeaway

When the book is broken and withdrawals are closed, acting against a market that isn't there only locks
in the loss and gives a reason to freeze the account. Sometimes the best thing you can do is nothing.
