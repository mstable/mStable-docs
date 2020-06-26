---
description: "\U0001F44B Welcome to mStable's docs. This is a live document that will be updated as mStable evolves. Currently, we aim to provide a high level overview of the protocol and its components."
---

# Getting Started

{% hint style="info" %}
These docs are still being worked on. Some parts may be unfinished or pending updates.
{% endhint %}

## What is mStable?

The mStable Standard is a protocol that makes stablecoins and other tokenized assets easy, robust and profitable. 

Three major problems confront stablecoin users: 

* significant fragmentation in same-peg assets
* lack of native yield when it is being increasingly demanded by users
* lack of insurance against permanent capital loss

Our products \(SWAP, SAVE and EARN\) are built specifically to address these pain-points. 

[mStable assets](mstable-assets/massets/) represent some underlying value peg and are [minted/redeemed](mstable-assets/massets/minting-and-redemption/) on-chain via smart contracts. mASSETS are backed 1:1 by a basket of existing tokenised same-base assets \(hereafter bASSETS\).

**Each mASSET is a liquidity share for its asset pool as well as a medium of exchange, unit of account and store of value in its own right.** 

Each mASSET has an outsized [native interest rate](mstable-assets/massets/native-interest-rate.md) that is derived from lending bASSETS on third party lending protocols combined with fees collected from mStable's SWAP product. 

Users can [swap](mstable-assets/massets/swapping.md) between bASSETS with **zero price slippage,** regardless of order size. For example, in mUSD, uses are able to swap 1 DAI for 1 USDC at no cost, except gas and a small fee. 

The protocol token [Meta](mstable-assets/functions/) \(MTA\) serves as insurance against permanent loss for all mASSETS. The token receives a percentage of all system revenue in compensation. In order to achieve long-term value of Meta, holders are motivated to seek stability through the diversification and growth of the system.

### **Characteristics**

* **Easy** - mStable is a one-stop solution for stablecoin users.
* **Robust** - Collateral is diversified, exterior to the system and ultimately insured by Meta. 
* **Stable** - mStable's liquidity shares are tokenized assets in their own right. 
* **Decentralized** - Meta embeds the incentives required to govern a decentralized system. Meta holders are paid when mStable grows securely.  
* **Built for Rapid Scaling** - 25% of Meta is emitted in a bootstrapping rewards pool. 

### Use cases

* **Yield and Return**
  * mASSETS earn an outsized yield \(interest + swap fees\). See [SAVE](mstable-assets/massets/native-interest-rate.md).
  * mStable is built so that those that use it or contribute to its growth are rewarded for doing so. See [Meta Rewards](meta-rewards-1/introduction/).
* **Traders & Arbitrageurs** 
  * Significant arbitrage opportunities will exist on the mStable Zero Slippage Swap. See [SWAP](mstable-assets/massets/swapping.md).
*  **Stablecoin Users** 
  * mStable issues assets that are more secure than the sum of their parts. Each mASSET diversifies risk between different asset issuers and stability mechanisms. The system itself is effectively __over-collateralised due to each mASSET being ultimately backed by Meta. See [EARN](mstable-assets/functions/).
* **SDK Integrations** 
  * **dApps:** mStable increases a dApp's user base while increasing usability. mStable allows dApps to accept several assets while presenting them in a more secure and user friendly way. For example, with the mStable [SDK](mstable-assets/interfacing-with-mstable/sdk.md), a dApp could accept USDC, DAI, TUSD, USDT, GUSD, USDx, CUSD and present the USD asset simply as _USD._  
  * **Futures exchanges:** instead of using a single stablecoin as the contract's basis, accept and settle in multiple. Decrease the possibility of mass liquidations due to a stablecoin peg loss
  * **Spot exchanges:** unite stablecoin liquidity into one pair: BTC/USD rather than BTC/USDT, BTC/USDC etc. 
  * **Participating dApps and exchanges receive** [**Meta**](meta-rewards-1/introduction/)**.**

    \*\*\*\*

### Features

* [Minting]()
* [Redemption](mstable-assets/massets/minting-and-redemption/#redemption)
* [Swaps](mstable-assets/massets/swapping.md)
* [Native Interest Rate](mstable-assets/massets/native-interest-rate.md)
* [Rewards](meta-rewards-1/introduction/)
* [Re-collateralisation](mstable-assets/functions/recollateralisation.md)
* [Meta Governance](mstable-assets/functions/governance.md) 
  * [Staking](meta-rewards-1/staking.md) 

{% hint style="success" %}
Now you've got the high level! Time to dig a little deeper.
{% endhint %}

