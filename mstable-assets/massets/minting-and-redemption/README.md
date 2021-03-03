---
description: >-
  Minting and redeeming is the exchange of a bAsset for its corresponding mAsset
  at a 1:1 ratio. Minting and redeeming increases or decreases the number of
  mAssets in circulation.
---

# Mint

## Minting

Each mAsset uses a smart contract to facilitate minting and redemption and hold its collateral.

* The user sends a bAsset to the mAsset's smart contract.
* For the USD mAsset, the underlying bAssets could be USDC, TUSD, USDT or sUSD pegged crypto assets.
* A mint is valid if it does not push any of the bAsset collateral levels past their predefined minimum or maximum weight.

Minting a mAsset offers immediate low slippage conversion of a bAsset into its corresponding mAsset.

All mAssets are ERC20 compliant, non custodial, and redeemable for the underlying bAsset\(s\) at any time.

## **Redeem**

In reverse, users redeem their mAssets from the mStable contracts.

* The user is able to specify which bAsset they wish to receive in return for an equivalent amount of their mAsset \(which is then burned, i.e. taken out of circulation\).
* A redemption is valid so long as the given bAsset\(s\) does not push any of the other bAssets below their minimum weights or over their maximum weights.

## **Examples**

### **The Basic Process of Minting a mAsset**

Assume there exists an mAsset called mExample, which has a basket with minimum and maximum weights defined as 5% and 35% for all bAssets respectively. The basket is comprised of 4 underlying bAssets \(Assets A, B, C, and D\).

To mint a single unit of mExample:

* Call the smart contract’s `mint` function;
* Supply a quantity of bAsset \(here, 100 of Asset A\).

The smart contract will validate that accepting 100 of Asset A will not push the total quantity of Asset A past its predefined maximum weight of 35% or below the minimum weight 5%.

Asset A is then transferred from the senders address. If the transfer is successful, the smart contract would in turn mint X units of mExample to the specified recipient, where X is computed by the bonding curve.

The user is therefore exchanging their asset for a mAsset of equal or very similar value.

### **The Basic Process of Redeeming a mAsset**

Continuing with mExample, which as before has 4 bAssets and the same weight limits.

To redeem 1000 mExample for a roughly equal amount of the underlying bAsset D:

* Call the `redeem` function on the mExample smart contract;
  * Specify that 1000 units of mAsset will be provided for a corresponding amount of Asset D, that is, the redemption asset. The final amount—let's call it Y—will be computed by the bonding curve.

A redemption is only valid if:

* It does not cause any bAsset to sink below minimum weight or rise above maximum weight.
* There are a sufficient number Asset D to pay out.

If the redemption is deemed valid, the contract retrieves 1000 mExample, which is burned, and the sender is credited with Y Asset D.

The fee for this single bAsset redemption is equal to the swap fee.

### **Functionality at weight limits**

In the event of one or more of mExample's bAssets being at minimum or maximum weight, minting and redemption options are modified. As before, there are 4 bAssets, minimum weights defined as 5% and maximum weights defined as 35% across them all. In this example, bAssets are at the following weights:

* Asset A - 35%
* Asset B - 30%
* Asset C - 30%
* Asset D - 5%

A user can always mint or redeem, even at minimum or maximum weight by sending or receiving one or a combination of bAssets that move the basket away from its minimum or maximum weight boundaries.

One way to redeem at max weights is via multi-redemption:

To redeem 100 mExample from the basket via a multi-redemption:

* Call the multi-redeem function `redeemMasset` on the mExample smart contract;
* Specify that 100 of mExample is to be redeemed.
* Receive 35 units of Asset A, 30 units of Assets B & C, and 5 units of Asset D.

{% hint style="info" %}
Minting and redemption is analogous for possible future mAssets \(e.g. mBTC, mGLD\)
{% endhint %}

