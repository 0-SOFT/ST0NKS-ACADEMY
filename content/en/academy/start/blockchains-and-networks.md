---
title: Blockchains, networks and swappers
description: The DEX groundwork: what a network is, what pays the fee, and why networks are isolated
slug: blockchains-and-networks
pair: blockchains-and-networks
section: start
date: 2026-09-08
topics: [start, dex]
---

Without this groundwork, working with decentralized venues becomes a set of actions you do by rote without understanding why they sometimes fail.

## A blockchain is not an exchange

A blockchain is a technology, not an exchange or a swapper. Its design is simple: a sequence of **blocks** numbered in order. Each block holds records of what happened.

| Concept | What it is |
|---|---|
| Block | a container of records under its own number |
| Transaction | one record: what was sent, where and to whom |
| Transaction hash | a unique identifier — the "receipt" confirming an action |
| Miners | those who gather records into a block and close it |

A transaction is not only a transfer: approving token use, confirming rights, sending a message are records too.

## Why a transaction can fail

Miners earn on the fee you pay to interact with the network. Set the fee too low and it is not worth a miner's while to include you in a block, so the transaction simply does not go through. This is not a fault but a mechanism: the fee is a bid in a contest for a place in the block.

## The network scanner

Every blockchain has its own explorer where everything happening is visible. The naming rule is simple: the network name plus the word Scan (Etherscan, BscScan, BaseScan, SolScan). The scanner is the main verification tool: it tells you which network a coin trades on and whether the contract address matches.

## Networks are not connected

Networks are like separate banks: not connected to one another, independent infrastructures. Two things follow: you need **bridges** to move between networks, and a wrong network choice means lost funds — what is sent to the wrong network simply does not exist for the recipient. The main networks are Ethereum, BNB Chain and Solana; the rest are secondary, with less liquidity.

## Swappers and aggregators

A **swapper** is a program for exchanging one token for another within a network (each network has its own). An **aggregator** is not a swapper but a route finder: it picks the cheapest exchange path across several swappers. A useful sign: if an aggregator finds no route at all, that signals a problem with the token, not an interface glitch.

## What pays the fee

The rule is simple: the fee is paid in the network's native token. As the network is named, so is the coin: ETH on Ethereum, BNB on BNB Chain, SOL on Solana.

> The exception is layer-2 networks (Arbitrum, Base, Linea): these are built on Ethereum, and their fee is paid in ETH. If you plan to work on them, keep ETH in the wallet, not the network's own token — there is none for the fee.

The fee is charged for any interaction: sending tokens, approving a wallet's connection to a DEX, the swap itself.

## What to remember

1. The fee is not a tax but a bid. Too low means the transaction will not go through.
2. The network scanner answers "where does this coin actually trade".
3. Networks are isolated. Moving between them is only possible by bridge.
4. Layer-2 networks charge the fee in ETH — the one exception to the naming rule.
