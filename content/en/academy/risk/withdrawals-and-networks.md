---
title: Deposits, withdrawals and networks
description: The check that cancels a trade outright, rather than merely shrinking it
slug: withdrawals-and-networks
pair: withdrawals-and-networks
section: risk
date: 2026-09-03
topics: [risk, withdrawals, networks]
---

A spread between two venues means something only if the coin can actually **move** between them.
This is the least-checked condition in arbitrage and the only one that cancels the trade completely.
Fees shrink a trade; a closed withdrawal ends it.

## One question that is really three

**Is withdrawal open on the buying venue?** Venues halt withdrawals for their own reasons —
maintenance, a node upgrade, suspicious activity, a decision about one particular asset. They are
under no obligation to announce it in advance.

**Is deposit open on the selling venue?** A separate switch, and it is sometimes off while
withdrawals work fine.

**Do the two share a network?** The same token often exists on several chains. If the buying venue
releases the coin on one chain only and the selling venue accepts another chain only, no transfer is
possible even though both "support the coin".

That third question is the least obvious and the most expensive. Sending on a chain the receiving
side does not support usually means the funds are gone with no recovery.

## What the scanner shows, and what it does not

We collect the deposit and withdrawal state per coin and per network and display it beside the pair.
It is the state **the venue reports**, and the boundary deserves saying out loud: a reported state is
not a verified one. A venue can keep withdrawals nominally enabled while requests queue for hours.
Our flag answers "is it permitted", not "how long will it take".

So use it the way it is meant: as a filter while choosing, not as a guarantee while trading.

## A fixed fee behaves differently from a percentage one

Venue fees scale with size, which is why subtracting them from a percentage spread works. A network
fee is a **fixed amount** and does not care how much you send:

| Transfer size | Network fee | Share |
|---|---|---|
| 100 | 1 | 1 % |
| 1,000 | 1 | 0.1 % |
| 10,000 | 1 | 0.01 % |

The same fee either eats the whole spread or disappears, depending on size alone. Which is why "a
good spread" does not exist on its own: it is good at some size and loss-making at another.

## Avoiding the transfer entirely

The transfer is not always necessary. With inventory already sitting on both venues, both legs open
at once, and balances are rebalanced later — not necessarily by moving that coin. The network fee and
the transit time both leave the arithmetic, and with them the largest part of the risk.

The price is capital pre-committed on both sides. That is not free: the same money could be working
elsewhere.

## In short

Before asking what a spread pays, ask whether the transfer is possible at all, and on which chain.
Fees reduce a spread. A closed withdrawal and mismatched networks remove it.
