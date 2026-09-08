---
title: Deposits and withdrawals via DEX wallets
description: Moving funds between an exchange and a non-custodial wallet, and the one rule — the network
slug: dex-wallets
pair: dex-wallets
section: start
date: 2026-09-08
topics: [start, dex]
---

To work with decentralized venues you must be able to move funds between an exchange and a non-custodial wallet — one whose keys only you hold.

## The one rule: the network

The exchange asks which network the operation runs on, and that is not a formality.

> Send funds on a network other than the one selected and the exchange will not recognize the payment or credit it. Recovery through support is theoretically possible but the odds are tiny.

A wallet address on Ethereum-compatible networks looks the same across them — which is exactly why the mistake goes unnoticed until the money is already sent. Check the network twice: on the exchange and in the wallet.

## Withdrawing from exchange to wallet

1. Open the withdrawal section, choose the coin, the "on-chain withdrawal" method and the network.
2. If needed, move funds to the account withdrawals are allowed from.
3. Copy the address from the wallet and paste it on the withdrawal page. Check the network fee.
4. Confirm with two codes: one from email and one from the authenticator app.

The transfer usually takes a few minutes, up to an hour or more under network load.

## Depositing from wallet to exchange

1. Open the deposit section, choose the asset and network. The exchange generates an address for that network.
2. Copy the address and, in the wallet, send the amount to it.
3. Before sending, check the address, network, amount and fee.

The deposit status is visible in both the wallet and the exchange; when the transfer completes it turns to "done".

## What to remember

- The network is chosen twice — on the exchange and in the wallet, and the values must match.
- The fee depends on the network: on layer-2 solutions it is far lower than on the main Ethereum network.
- Withdrawal needs 2FA — both the email code and the app code.
