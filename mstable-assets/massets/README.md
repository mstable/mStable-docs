---
description: "\U0001F4B0 mStable unites stablecoins and other tokenised assets into non custodial and higher yielding instruments. Our first mAsset is a fiat currency (mUSD)."
---

# mAssets

## Overview

mStable can support numerous mAssets. Each mAsset is pegged to a unique asset, such as fiat currency \(US Dollar\) or a cryptocurrency like Bitcoin. mAssets are backed by a basket of existing whitelisted tokenised assets of that same peg, and held by the user \(ie they are **non-custodial**\). 

mAssets are [minted/redeemed](minting-and-redemption/) permissionlessly and on-chain via the mStable smart contracts. 

* **To** [**mint**](minting-and-redemption/#minting) **an mUSD**, for example, a user sends 1 USDT and receives 1 mUSD in return. ****
* **To** [**redeem**](minting-and-redemption/#redemption)**,** the user sends an mUSD to the contract and can choose which bAsset to receive in return for the swap fee. In the current implementation, if maximum weights are reached, the user will receive a mix of bAssets that are reflective of the current basket composition at no fee. The mAsset is then burned \(i.e. taken out of circulation\). 

Each bAsset will have a max weight that determines its highest possible weighting in that basket. 

A maximum weight is important because:

* It creates an upper-bound to the amount of mAssets a user may mint for an undervalued bAsset. 
* It creates an upper-bound to the amount of bAssets a user may swap in pursuit of arbitrage profits. 

The maximum weight can be adjusted through mStable’s governance system in response to new information or changing market conditions. 

New bAssets can be added should they be deemed secure and stable by the governors. Conversely, a bAsset can be removed should the governance system consider it too risky for inclusion in a basket. 

Possible future mAssets:

* mBTC Ⓑ
* mGLD🏆
* mEUR __💶 
* mGBP 💷

