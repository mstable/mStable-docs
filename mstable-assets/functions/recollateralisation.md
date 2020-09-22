---
description: "\U0001F3E5 Each mStable asset is stronger than the sum of its parts. Re-collateralization would protect the basket in the event of a bASSET losing its peg."
---

# Re-collateralization Proposal

{% hint style="info" %}
The founding team will propose this feature to be launched in [Phase 2](../../protocol/versioning.md#phase-2) of the protocol
{% endhint %}

## Introduction

mStable creates assets that are stronger than the sum of their parts. A core reason for this would be a re-collateralization mechanism. Meta could be used to effectively over-collateralise mASSETS. 

If a collateral basket asset - a bASSET - loses its peg, mStable could purge that asset and recover lost value by selling Meta for the outstanding mASSET. 

The purchased mASSET is subsequently burned. This continues until there is an equal amount of outstanding mASSETS to the amount of collateral in the basket, re-collateralizing the system.

For example, if TUSD breaks its peg and falls to 60 cents, governors can choose to remove it from the mUSD basket. During this process, the system for that particular mASSET effectively stops, with swaps being paused and forging being restricted. The mASSET is re-collateralized by selling Meta for mUSD until the system returns to full collateralization, or as a last resort "failing" the mASSET should the process be unsuccessful \(i.e. mStable will fail a mASSET before failing Meta\).

This functionality is still in development, and will be described in more detail as implementation approaches.

