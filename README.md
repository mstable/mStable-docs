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

## What is mStable?

mStable is a collection of **autonomous, decentralised,** and **non-custodial** smart contracts. It is built on Ethereum.

mStable was created to address three major problems that confront stablecoin users:

* significant fragmentation in same-peg stablecoins \(there are currently over 5 major USD pegged stablecoins on Ethereum for example\)
* lack of yield in fiat currencies and stablecoins
* lack of protection against permanent capital loss in stablecoins

mStable assets \(hereafter mAssets\) represent some underlying value peg and are minted/redeemed on-chain via smart contracts.

A user minting an mAsset interacts only with the mStable contracts, which are non-custodial. This means that no third party ever takes custody of a user's assets. In other words, mStable is a "peer to pool" protocol, where the pool of deposited stablecoins "live" in a non-custodial smart contracts.

mAssets are fully backed by a basket of existing stablecoins \(hereafter bAssets\).

Each mAsset represents a share of liquidity in that mAsset's basket as well as a stablecoin in its own right. A mAsset can be used as a medium of exchange, unit of account and store of value.

Each mAsset is designed to produce an above-average native interest rate \(although this of course is never guaranteed\). This rate is derived from the mStable contracts autonomously and programatically lending bAssets to third party lending protocols, generating interest income. The mStable contracts simultaneously allow for bAssets to be exchanged or "swapped" for a fee. All interest and exchange income is automatically and programmatically sent to mAsset _savers_.

The mStable protocol is governed by Meta \(`MTA`\) Governors. Those who have the `MTA` token can stake \(i.e. deposit in a governance smart contract\) their tokens to become protocol governors, allowing them to govern the mStable protocol.

**Every participant who interacts with mStable has the option to earn** `MTA`**, either through contributing to its utility \(through EARN\) or by saving a mAsset \(through SAVE's deposit box\).** `MTA` **is emitted in this way to facilitate decentralised, collective and user-driven governance.**

### **Characteristics**

* **Non Custodial** - mStable users always have custody of their funds.
* **Robust** - Collateral is diversified across multiple stablecoins.
* **Stable** - mAsset are stablecoins in their own right.
* **Decentralised** - `MTA` governs mStable. Every user can earn `MTA` and participate in mStable's collective governance.

### Use cases

* **Composable** **Yield**
  * mAssets should earn an outsized yield \(derived from interest income + swap fees + other income\). The imUSD saving token can be used as a low volatility, secure and yielding collateral throughout DeFi. See SAVE.
* **Traders & Arbitrageurs**
  * Traders can swap stablecoins efficiently using SWAP.
  * Arbitrage opportunities exist using mStable's swap. 
* **Security conscious stablecoin users**
  * mStable issues assets aim to be more secure than the sum of their parts. Each mAsset diversifies risk between different asset issuers and stability mechanisms, and caps exposure to any one asset.

### Features

* [Minting and Redemption](mstable-assets/massets/minting-and-redemption/#redemption)
* [Swaps](mstable-assets/massets/swapping.md)
* [Native Interest Rate](mstable-assets/massets/native-interest-rate.md)
* [Meta Governance](mstable-assets/functions/governance.md) 

{% hint style="success" %}
Now you've got the high level! Time to dig a little deeper.
{% endhint %}

