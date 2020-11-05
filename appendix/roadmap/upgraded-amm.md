---
description: "\U0001F504 An upgraded AMM with infinite liquidity for redemptions & swaps"
---

# Upgraded AMM

### Summary

We are aware of certain limitations in the current implementation of the protocol. The bAssets that hover the lowest below peg fill the basket, and those that hover the highest above peg, e.g. DAI, are constantly drained out of the basket, damaging the liquidity and composability of mStable. mStable needs a new AMM that gives mStable infinite liquidity, and thus preserves composability, whilst still managing the risk of peg loss of an underlying bAsset.

To achieve this, one of the key priorities is a more capital efficient and dynamic automated market maker \(AMM\). Our solution retains the concept of a straight line bonding curve while the weights are within a desired range, and applies a penalty or a bonus depending on the situation - more information about this will be released in a dedicated blog post soon.

_We expect this to be implemented by late December 2020, assuming the MTA Governors approval._





