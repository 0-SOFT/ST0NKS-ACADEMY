---
title: Ticker collisions, or the spread that is not there
description: Why the largest numbers in any arbitrage scanner usually mean two different coins wearing one name
slug: ticker-collision
pair: ticker-collision
section: risk
date: 2026-09-03
topics: [risk, collision, spread]
---

Sort any arbitrage scanner by spread, look at the top rows, and you will find tens or hundreds of
percent. That is almost never an opportunity. It is a **ticker collision**: two venues listing two
**different coins** under the same symbol.

## Why symbols collide

A ticker is not a global identifier. It is a short label each venue picks for itself at listing
time. There are few three- and four-letter combinations and many projects, so the same label ends up
attached to different tokens in different places. Nobody is breaking a rule here — there is no
global ticker registry to break.

For arbitrage this is the worst possible error, because it disguises itself as the best possible
opportunity. A pair assembled from two different coins **is not hedged**. You bought one asset and
sold another; what you hold is two open directional positions, not a closed pair.

## How it is detected

The signal is straightforward: **a leg whose price disagrees with the same ticker everywhere else.**

Our scanner first gathers every price for the token and takes the **median** — the price most venues
agree on. Each leg is then compared against it, and a leg that sits multiples away is an outlier. A
pair containing an outlier is flagged as a possible collision.

The median is not an arbitrary choice. A mean is dragged by a single extreme value, and the extreme
value is precisely what we are hunting: the statistic would be distorted by the thing it is meant to
expose. A median does not care about one strange participant.

**Thin tokens are a separate case.** With a listing on only two venues there is no median: there are
two prices, and either has an equal claim to being the right one. There the two legs are compared
against each other and the flag follows their ratio. That is weaker, and the weakness is worth
stating plainly — with two prices, telling "a rare coin is dearer on one venue" apart from "these are
two different coins" is impossible in principle, not merely impossible for us.

## What the scanner does with them

Flagged pairs are **hidden by default**. Not to keep data from you: because a mirage always occupies
the top of the table. It produces the biggest numbers, so without hiding, the first screen would
consist of nothing else.

You can switch them on, and they stay marked when you do. The flag reads "**possible** collision"
deliberately — the mechanism cannot prove two coins are the same coin. It only sees prices that fail
to agree.

## Checking one yourself

The flag is a reason to look, not a verdict. Three steps:

1. Open the pair page and read both legs. Do the prices differ by percent, or by multiples?
2. Compare the **contract address** on both venues. Different addresses mean different tokens, and
   that settles it.
3. Look at traded volume. A real coin showing a hundred percent of spread on twenty dollars of volume
   is not a spread — it is one stray order.

The third step earns its place independently: the spread is computed from the top of the book, and
the top of the book can rest on an amusing quantity.

## In short

A large spread is an instruction to check **whether this is one coin**, not an instruction to trade.
The rule that saves the most money is a boring one: the higher the spread, the likelier you are
looking at two different things that happen to share a name.
