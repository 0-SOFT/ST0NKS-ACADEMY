---
title: "Index price: why a pair falls apart"
description: Not the "real price of the coin" but an average over a list the exchange picks itself
slug: index-price
pair: index-price
section: mechanics
date: 2026-09-08
topics: [mechanics, index]
---

The index price is not the "real price of the coin." It is a weighted average over a list of venues that
EACH exchange builds itself. The lists do not match, and exchanges change them. Hence a whole class of
pairs that never converge.

## Index components

Each exchange has a list of price sources and a weight for each. It is published in the interface but
looks so technical that almost no one reads it. Yet it is what decides where the futures mark price will
be pulled to.

## Why this breaks a pair

The futures price converges to the index through trading on the venues the index is built from. If your
second leg is on an exchange that is not in that list, there is nothing for the prices to converge
through: the index is pulled from other venues, and yours lives on its own.

## The takeaway

Before a futures pair, look at the index components of both legs: if the prices are not tied to a common
source, the convergence you are betting on may never come.
