---
description: >-
  ⚖️ mStable governors can alter bAsset maximum weights according to new market
  conditions or information.
---

# Basket Adjustment

Governance will control the addition/removal of bAssets and set their maximum weights. 

A Basket Adjustment occurs when Governance chooses to change the maximum weight of a bAsset. 

Secondly, a basket adjustment can occur when a bAsset is deemed unfit for inclusion. In this case, [Governance](../../functions/governance.md) will be able to purge that bAsset entirely. 

### Standard Basket Adjustment  

Occurs when:

* A bAsset's max weight is changed by Governance. 

The basket adjustment mechanism allows [Forging](./) and [Swapping](../swapping.md) demand to do the heavy lifting to execute the transition:

* [Minting](./) validity remains the same. This means that if Governance lowers the maximum weight of a bAsset so that it is below its current collateral level, minting is temporary disabled with this bAsset until it is below its maximum weight.
* The weight is lowered through allowing free swaps from that bAsset and only allowing multi-proportional redemption. 
* Users are not allowed to swap into an overweight bAsset.

### Adding bAssets

Governance has the power to add bAssets to a mAsset's contract and dictate its maximum weight.  

### Removing bAssets

The removal of a bAsset is deemed complete when its collateral level and max weight = 0. 

