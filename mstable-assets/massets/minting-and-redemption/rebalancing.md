---
description: >-
  mStable governors can alter bAsset maximum weights according to new market
  conditions or information.
---

# Basket Adjustment

Meta Governors can alter bAsset maximum weights according to new market conditions or information.

Meta Governors control the addition/removal of bAssets and set their maximum weights.

A Basket Adjustment occurs when Meta Governors choose to change the maximum weight of a bAsset.

Secondly, a basket adjustment can occur when a bAsset is deemed unfit for inclusion. In this case, Meta Governors will be able to remove that bAsset entirely.

### **Adding bAssets**

Meta Governors have the power to vote to add bAssets to a mAsset's contract and dictate its maximum weight.

### **Removing bAssets**

Meta Governors have the power to add bAssets to a mAsset's contract and dictate its maximum weight. The removal of a bAsset is deemed complete when its collateral level and max weight = 0.

### Changing Bonding Curve Parameters

Meta Governors have the power to change the parameters which determine the shape of the bonding curve and the prices offered by the AMM.

### Setting a Total Value Locked \(TVL\) Cap

Meta Governors have the power to set a cap to mAsset supply, namely limit the amount mAsset that can be minted.

Note: mBTC is released with a guarded launch procedure, which features a TVL cap that gradually increases over a course of 7 weeks, and then is finally lifted. This is achieved programmatically, and does not require manual intervention. This is done to launch new features in a more secure and limited environment.

### Setting Fees

Meta Governors have the power to set the percentage of swap and redemption fees on mAssets.

Note: During the guarded launch, fees on mBTC will start at 20 bps, decrease linearly throughout the period, and settle at 4 bps after 7 weeks.

