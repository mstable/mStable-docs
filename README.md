---
description: "\U0001F44B Welcome to mStable's docs. This is a live document that will be updated as mStable evolves. Currently, we aim to provide a high level overview of the protocol and its existing components."
---

# Getting Started

{% hint style="info" %}
These docs are still being worked on. Some parts may be unfinished or pending updates.
{% endhint %}

## What is mStable?

mStable provides **autonomous** and **non-custodial** stablecoin infrastructure.

Three major problems confront stablecoin users: 

* significant fragmentation in same-peg assets
* lack of native yield when it is being increasingly demanded by users
* lack of protection against permanent capital loss

Our products \(MINT, SWAP, SAVE, and EARN\) are built specifically to address these pain-points. 

[mStable assets](mstable-assets/massets/) \(hereafter mAssets\) represent some underlying value peg and are [minted/redeemed](mstable-assets/massets/minting-and-redemption/) on-chain via smart contracts. mAssets are backed 1:1 by a basket of existing tokenised same-base assets \(hereafter bAssets\).

**Each mAsset is a liquidity share for its asset pool as well as a medium of exchange, unit of account and store of value in its own right.** 

Each mAsset has an outsized [native interest rate](mstable-assets/massets/native-interest-rate.md) that is derived from lending bAssets on third party lending protocols, fees collected from mStable's SWAP product, and other sources of income. 

Users can [swap](mstable-assets/massets/swapping.md) between bAssets with **zero price slippage,** regardless of order size. For example, in mUSD, uses are able to swap 1 DAI for 1 USDC at no cost, except gas and a small fee. 

Those who hold Meta can stake their tokens to become governors, allowing them to participate in governance of the system. In order to achieve long-term value of Meta, these governors are motivated to seek stability through the growth and diversification of mStable.

### **Characteristics**

* **Easy** - mStable is a one-stop solution for stablecoin users.
* **Robust** - Collateral is diversified, with risk management for underlying assets. 
* **Stable** - mStable's liquidity shares are tokenized assets in their own right. 
* **Decentralized** - Meta embeds the incentives required to govern a decentralized system.
* **Built for Rapid Scaling** - The majority of Meta will be emitted via[ Public Rewards](meta-rewards-1/introduction/). 

### Use cases

* **Yield and Return**
  * mAssets earn an outsized yield \(interest + swap fees + other income\). See [SAVE](mstable-assets/massets/native-interest-rate.md).
  * mStable is built so that those that use it or contribute to its growth are rewarded for doing so. See [Meta Rewards](meta-rewards-1/introduction/).
* **Traders & Arbitrageurs** 
  * Significant arbitrage opportunities exist using mStable's Zero Slippage swaps. See [SWAP](mstable-assets/massets/swapping.md).
*  **Stablecoin Users** 
  * mStable issues assets that are more secure than the sum of their parts. Each mAsset diversifies risk between different asset issuers and stability mechanisms. The system itself is effectively __over-collateralised due to each mAsset being ultimately backed by Meta. See [EARN](mstable-assets/functions/).
* **SDK Integrations** 
  * mStable allows dApps to accept several assets while presenting them in a more secure and user friendly way. This product is yet to be built, but may have potential applications for DeFi dApps and crypto exchanges. 

### Features

* [Minting and Redemption](mstable-assets/massets/minting-and-redemption/#redemption)
* [Swaps](mstable-assets/massets/swapping.md)
* [Native Interest Rate](mstable-assets/massets/native-interest-rate.md)
* [Rewards](meta-rewards-1/introduction/)
* [Meta Governance](mstable-assets/functions/governance.md) 

{% hint style="success" %}
Now you've got the high level! Time to dig a little deeper.
{% endhint %}

