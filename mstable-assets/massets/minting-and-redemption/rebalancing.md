---
description: >-
  ⚖️ mStable can alter bASSET maximum weights according to new market conditions
  or information.
---

# Basket Adjustment

Governance will control the addition/removal of bASSETS and set their maximum weights. 

A Basket Adjustment occurs when Governance chooses to change the maximum weight of a bASSET. 

Secondly, a basket adjustment can occur when a bASSET is deemed unfit for inclusion. In this case, [Governance](../../functions/governance.md) will be able to purge that bASSET entirely. 

### Standard Basket Adjustment  

Occurs when:

* A bASSET'S max weight is changed by Governance. 

The basket adjustment mechanism allows [Forging](./) and [Swapping](../swapping.md) demand to do the heavy lifting:

* [Minting](./) validity remains the same. This means that if Governance lowers the maximum weight of a bASSET so that it is below its current collateral level, minting is temporary disabled with this bASSET until it is below its maximum weight.
* The weight is lowered through allowing free swaps into that bASSET and only allowing multi-proportional redemption. 
* Users are not allowed to swap out of an overweight bASSET.

### Adding bASSETS

Governance has the power to add bASSETS to a mASSET contract and dictate its maximum weight.  

### Removing bASSET

The removal of a bASSET is deemed complete when its collateral level and max weight = 0. See Expedited Rebalance below. 

## **Expedited Rebalance**

It may be deemed necessary by Governors to expedite an adjustment and ultimately remove a bASSET entirely. This will be possible through liquidating the given bASSET through a two phased auction mechanism described in [Re-collateralisation](../../functions/recollateralisation.md). 

