---
description: >-
  Welcome to mStable's docs. This is a live document that will be updated as
  mStable evolves. Currently, we aim to provide a high level overview of the
  protocol and its existing components.
---

# Getting Started

{% hint style="info" %}
These docs are still being worked on. Some parts may be unfinished or pending updates.
{% endhint %}

### 1. What is mStable?

mStable is an autonomous and non-custodial infrastructure for pegged-value crypto assets. 

It is built on Ethereum and Polygon. mStable assets \(mAssets\) are built to an autonomous and non-custodial pegged asset layer for Decentralised Finance \(DeFi\). 

mStable was created to address three major problems that confront pegged crypto asset users:

* significant fragmentation in same-peg crypto assets \(there are currently over 5 major USD pegged crypto assets on Ethereum for example\)
* lack of yield in fiat currencies and pegged crypto assets
* lack of protection against permanent capital loss in pegged crypto assets

mAssets represent some underlying value peg and are minted/redeemed on-chain via smart contracts.

A user minting an mAsset interacts only with the mStable contracts, which are non-custodial. This means that no third party ever takes custody of a user's assets. In other words, mStable is a "peer to pool" protocol, where the pool "lives" in a non-custodial smart contract.

mAssets are fully backed by a basket of existing tokenised same-base assets \(hereafter bAssets\).

Each mAsset represents a share of liquidity in that mAsset's pool as well as a pegged crypto asset in its own right. A mAsset can be used as a medium of exchange, unit of account and store of value.

Each mAsset should produce an outsized native interest rate \(although this of course if never guaranteed\). This rate is derived from the mStable contracts autonomously and programatically lending bAssets to third party lending protocols, generating interest income. The mStable contracts simultaneously allow for bAssets to be exchanged or "swapped" for a fee. All interest and exchange income is automatically and programmatically sent to mAsset _savers_.

The mStable protocol is governed by Meta \(`MTA`\) Governors. Those who have the `MTA` token can stake \(i.e. deposit in a governance smart contract\) their tokens to become protocol governors, allowing them to govern the mStable protocol.

**Every participant who interacts with mStable has the option to earn** `MTA`**, either through contributing to its utility \(through Earn\) or by saving a mAsset \(through Save\).** `MTA` **is emitted in this way to facilitate decentralised, collective and user-driven governance.**

### **Characteristics**

* **Non-custodial** - mStable users always have custody of their funds.
* **Robust** - Collateral is diversified across multiple pegged crypto assets.
* **Stable** - mAsset are pegged crypto assets in their own right.
* **Decentralised** - `MTA` governs mStable. Every user can earn `MTA` and participate in mStable's collective governance.

### Use cases

* **Composable** **Yield**
  * mAssets should earn an outsized yield \(derived from interest income + swap fees + other income\). See Save.
* **Traders & Arbitrageurs**
  * Arbitrage opportunities exist using mStable's swap. See Swap.
  * Traders can swap pegged crypto assets efficiently using Swap.
* **Security conscious pegged crypto asset users**
  * mStable issues assets that are designed to be more secure than the sum of their parts. Each mAsset diversifies risk between different asset issuers and stability mechanisms, and caps exposure to any one asset.

### Features

* [Minting and Redemption](mstable-assets/massets/minting-and-redemption/#redemption)
* [Swaps](mstable-assets/massets/swapping.md)
* [Native Interest Rate](mstable-assets/massets/native-interest-rate.md)
* [Meta Governance](mstable-assets/functions/governance.md) 

{% hint style="success" %}
Now you've got the high level! Time to dig a little deeper.
{% endhint %}

