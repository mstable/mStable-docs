---
description: >-
  ➡️ Forging (Minting & Redeeming) is the exchange of a whitelisted bASSET for
  its corresponding mASSET at a 1:1 ratio. Forging increases or decreases the
  number of mASSETS in circulation.
---

# MINT

## Minting

Each mASSET will use a smart contract to facilitate minting and redemption and hold its collateral. 

* To mint an mStable asset, a user calls the `mint` function of that mASSET contract. 
* The user then sends any of the underlying whitelisted tokens to the smart contract of that asset. 
  * For the USD asset, the underlying bASSET could be USDC, TUSD, USDT, DAI, and so on.
* A mint is valid if it does not push any of the bASSET collateral levels past their predefined maximum weight. 

Minting a mASSET offers optionality and immediate 1:1 \(zero slippage\) conversion of a bASSET into its corresponding mASSET. 

For example, if you send 100 DAI to the mUSD contract, you will receive 100 redeemable mUSD back. Minting costs you nothing but gas .

The newly minting mASSET is more secure than the corresponding bASSET as it is backed by several other assets as well as by the [mStable protocol token](../../functions/recollateralisation.md) Meta. Users must have a mASSET in order to take advantage of mStable [native interest rate](../native-interest-rate.md).

The mASSET is ERC20 compliant and the user is able to [redeem](./#redemption) it for the underlying bASSETS at any time. 

## Redemption

In reverse, users redeem their mASSET by calling a `redeem` function on the mASSET contract. 

* The user is able to specify which bASSET they wish to receive in return for an equivalent amount of their mASSET \(which is then burned\).
* A redemption is valid so long as the given bASSET\(s\) does not push any of the other bASSETS over their maximum weights. When redeeming for a single bASSET, a fee equal to the swap fee is charged. 
* If a bASSET is at maximum weight, the system enforces "multi-proportional redemption". At no fee, the user receives a proportional representation of bASSETS.
* This means that even in the event of a peg loss, the system retains value without requiring oracles. 

## DEX Integrations

To provide further optionality during the Forging process, we can capitalise on existing on-chain exchanges \(or “DEXs”\).  These exchanges can facilitate minting across a broad variety of assets \(such as ETH\), which will then be used to purchase the most optimal bASSET for minting.

The same mechanism can be used in the redemption process wherein the user may wish to receive a particular output token\(s\). These tokens would then be traded on a DEX before ultimately returning the output to the user. This can be enabled in one transaction.

## Examples

### The Basic Process of Minting a mASSET

Assume there exists an mASSET called mExample, which has a basket with **maximum weights** defined as 35% for all bASSETS. The basket is comprised of 4 underlying bASSETS \(Assets A, B, C, and D\). 

To mint a single unit of mExample:

* Call the smart contract’s `mint` function;
* Supply a quantity of bASSET \(here, 100 of Asset A\). 

The smart contract will validate that accepting 100 of Asset A will not push the total quantity of Asset A past its predefined maximum weight of 35%.

Asset A is then transferred from the senders address. If the transfer is successful, the smart contract would in turn mint 100 units of mExample to the specified recipient. 

The user is therefore exchanging their asset for a mASSET of equal or very similar value. 

### **The** Basic **Process of Redeeming a mASSET**

Continuing with mExample, which as before has 4 bASSETS and **maximum weights** defined as 35% across them all. 

To redeem 1000 mExample for 1000 of the underlying bASSET D:

* Call the `redeem` function on the mExample smart contract;
* Specify that 1000 of Asset D is desired as the redemption asset. 

A redemption is only valid if:

* It does not cause any bASSET to rise above its `max weighting.` 
* There are a sufficient number Asset D to pay out.

If the redemption is deemed valid, the contract retrieves 1000 mExample, which is burned, and the sender is credited with 1000 Asset D.  

The fee for this single bASSET redemption is equal to the swap fee.  

### **Forging at maximum weights**

In the event of one or more of mExample's bASSETS being at maximum weight, minting and redemption options are modified. As before, there are 4 bASSETS and **maximum weights** defined as 35% across them all. In this example, bASSETS are at the following weights:

* **Asset A - 35%** 
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

