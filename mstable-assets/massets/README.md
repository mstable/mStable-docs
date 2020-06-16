---
description: "\U0001F4B0 mStable unites stablecoins and other tokenised assets into more useful and higher yielding instruments. Our first assets include a fiat currency (mUSD), a commodity (mGLD) and Bitcoin (mBTC)."
---

# mASSETS

## Overview

mStable can support numerous mASSETS. Each mASSET is pegged to a unique asset, such as fiat currency \(US Dollar, Japanese Yen\), a Consumer Price Index, a commodity like Gold, or a cryptocurrency like Bitcoin. 

Each mASSET is backed by a basket of existing whitelisted tokenised assets of that same peg. 

mASSETS are [minted/redeemed](minting-and-redemption/) permissionlessly and on-chain via smart contracts. 

* **To** [**mint**](minting-and-redemption/#minting) **an mUSD**, for example, a user sends 1 USDT and receives 1 mUSD in return. ****
* **To** [**redeem**](minting-and-redemption/#redemption)**,** the user sends an mUSD to the contract and can choose which bASSET to receive in return for the swap fee. If maximum weights are breached, the user will receive a series of bASSETS that are reflective of the current basket composition at no fee. The mASSET is then burned \(i.e. taken out of circulation\). 

Each bASSET will have a max weight that determines its highest possible weighting in that basket. 

A maximum weight is important as:

* Its impact on Meta in the event of a peg loss and re-collateralisation is capped;
* It creates an upper-bound to the amount of mASSETS a user may mint for an undervalued bASSET. 
* It creates an upper-bound to the amount of bASSETs a user may swap in pursuit of arbitrage profits. 

The maximum weight can be adjusted through mStable’s governance system in response to new information or changing market conditions. 

New bASSETS can be added should they be deemed secure and stable by the governance system. Conversely, a bASSET can be removed should the governance system consider it too risky for inclusion in a basket. 

**Every mASSET is protected by the protocol token** [**Meta**](../functions/) **which serves as a backstop for all mStable assets.**

Possible future mAssets:

* mUSD __💵 
* mBTC Ⓑ
* mGLD🏆
* mEUR __💶 
* mGBP 💷

#### **Metastable Ⓜ**

Once a sufficient number of mASSETS have been created and scaled, the protocol will enable the creation of a basket of mASSETS called Metastable. It will represent a global diversified basket of pegged assets - a unit of account for the digital world.  

As with other mASSETS, the Meta holders will be the governors of Metastable. However, there will be no fees for the Metastable asset and Meta will not act as a direct backstop to Metastable. This is because the underlying assets of Metastable are mASSETS \(which already incur fees and can be re-collateralised by Meta\).

