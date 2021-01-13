---
description: >-
  ➡️ Forging (Minting & Redeeming) is the exchange of a whitelisted bAsset for
  its corresponding mAsset at a 1:1 ratio. Forging increases or decreases the
  number of mAssets in circulation.
---

# MINT

## Minting

Each mAsset uses a smart contract to facilitate minting and redemption and hold its collateral.

* The user sends a bAsset the smart contract of that mAsset asset.
* For the USD mAsset, the underlying bAsset could be USDC, TUSD, USDT or sUSD stablecoins.
* A mint is valid if it does not push any of the bAsset collateral levels past their predefined maximum weight.

Minting a mAsset offers immediate 1:1 \(zero slippage\) conversion of a bAsset into its corresponding mAsset.

All mAssets are ERC20 compliant, non custodial, and redeemable for the underlying bAsset\(s\) at any time.

## Redemption

In reverse, users redeem their mAssets from the mStable contracts.

* The user is able to specify which bAsset they wish to receive in return for an equivalent amount of their mAsset \(which is then burned, i.e. taken out of circulation\).
* A redemption is valid so long as the given bAsset\(s\) does not push any of the other bAssets over their maximum weights.
* If a bAsset is at maximum weight, the system enforces "multi-proportional redemption". The user receives a proportional representation of bAssets, and pays a fee of 3 basis points.

## Examples

### **The Process of Minting a mAsset**

Assume there exists an mAsset called mExample, which has a basket with maximum weights defined as 35% for all bAssets. The basket is comprised of 4 underlying bAssets \(Assets A, B, C, and D\).

To mint a single unit of mExample:

* Call the smart contract’s `mint` function;
* Supply a quantity of bAsset \(here, 100 of Asset A\).

The smart contract will validate that accepting 100 of Asset A will not push the total quantity of Asset A past its predefined maximum weight of 35%.

Asset A is then transferred from the senders address. If the transfer is successful, the smart contract would in turn mint 100 units of mExample to the specified recipient.

The user is therefore exchanging their asset for a mAsset of equal or very similar value.

### **The Process of Redeeming a mAsset**

Continuing with mExample, which as before has 4 bAssets and maximum weights defined as 35% across them all.

To redeem 1000 mExample for 1000 of the underlying bAsset D:

* Call the `redeem` function on the mExample smart contract;
* Specify that 1000 of Asset D is desired as the redemption asset.

A redemption is only valid if:

* It does not cause any bAsset to rise above its `max weighting.`
* There are a sufficient number Asset D to pay out.

If the redemption is deemed valid, the contract retrieves 1000 mExample, which is burned, and the sender is credited with 1000 Asset D.

The fee for this single bAsset redemption is equal to the swap fee.

### **Functionality at maximum weights**

In the event of one or more of mExample's bAssets being at maximum weight, minting and redemption options are modified. As before, there are 4 bAssets and maximum weights defined as 35% across them all. In this example, bAssets are at the following weights:

* Asset A - 35%
* Asset B - 30%
* Asset C - 30%
* Asset D - 5%

As Asset A is at its maximum weight, users cannot redeem any of the other assets individually \(as this would push Asset A proportionally over 35% of the basket\). For the same reason, they cannot mint with Asset A. In this scenario, "multi" minting and redemption is now enforced.

To redeem 100 mExample from the basket:

* Call the `multi` redeem function on the mExample smart contract;
* Specify that 100 of mExample is to be redeemed.
* Receive 35 units of Asset A, 30 units of Assets B & C, and 5 units of Asset D.

{% hint style="info" %}
The Forging process will be analogous for mGLD, mEUR, mBTC and so on.
{% endhint %}

