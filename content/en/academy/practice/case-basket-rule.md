---
title: "Case study: why a spread ran from zero to 13%"
description: Exchanges compute funding differently — and that breaks a "symmetric" pair
slug: case-basket-rule
pair: case-basket-rule
section: practice
date: 2026-09-08
topics: [practice, funding]
---

A spread between two exchanges ran from zero to 13% — not because the market moved against the trade,
but because the two venues compute the funding rate differently.

## An observed rule of two groups

Practitioners split exchanges into two groups by how funding behaves on them. Some venues are convenient
to hold as the long leg, others as the short. This is not an official classification but a practical
observation: build a pair "the wrong way round" and you get funding that works against you.

## Why the groups exist at all

The cause is technical: different funding formulas. Some exchanges pull the mark price toward the index
more firmly through funding, others more softly — so on a single market move their prices diverge rather
than converge. A pair built without accounting for this looks symmetric but is in fact stretched one
way.

## The takeaway

The exact membership of the groups changes over time, so what matters is not a list but the cause:
funding is computed differently, and the two legs must be chosen so funding works FOR the position, not
against it.
