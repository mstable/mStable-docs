---
description: "\U0001F3E5 Each mStable asset is stronger than the sum of its parts. Re-collateralization protects the basket in the event of a bASSET losing its peg."
---

# Re-collateralization

{% hint style="info" %}
This feature will be launched in [Phase 2](../../protocol/versioning.md#phase-2) of the protocol
{% endhint %}

## Introduction

mStable creates assets that are stronger than the sum of their parts. A core reason for this is mStable's re-collateralization mechanism. Meta is used to effectively over-collateralise mASSETS. 

If a collateral basket asset - a bASSET - loses its peg, mStable can purge that asset and recover lost value by selling Meta for the outstanding mASSET. 

The purchased mASSET is subsequently burned. This continues until there is an equal amount of outstanding mASSETS to the amount of collateral in the basket, re-collateralizing the system.

For example, if TUSD breaks its peg and falls to 60 cents, governors can choose to remove it from the mUSD basket. During this process, the system for that particular mASSET effectively stops, with swaps being paused and forging being restricted. The mASSET is re-collateralized by selling Meta for mUSD until the system returns to full collateralization, or as a last resort "failing" the mASSET should the process be unsuccessful \(i.e. mStable will fail a mASSET before failing Meta\).

## Process

### Governors Declare Peg Loss

In order for the re-collateralization process to begin, human governors in the system must declare that a bASSET has lost its peg. This may not be a straightforward decision and thus may take time, as it can be hard to know the underlying reasons why a stablecoin may have deviated from its peg at any given point in time. Until this point, the system is protected against others trying to game it by it through **maximum weight rules and enforced `multi` redemption.**

As the mStable contracts only need to care about the weightings of bASSETS in the basket, and not their prices, to maintain its security, this re-collateralization ****detection ****system **does not need a price oracle.** 

During a re-collateralization, governors have three options to choose from:

* Return system to maximum weight state \(assumes bASSET has returned to its peg\)
* Delay decision
* Initiate bASSET auction

###  **bASSET A**uction

If the proposal to start the re-collateralization process is approved, the affected bASSET is auctioned for its mASSET through an OpenIPO format of a Dutch auction. The collected mASSET will be burned, reducing its supply.

### Meta Auction

As it is unlikely that sufficient mASSET will be burned through this process, there is a secondary auction. In this stage, the same OpenIPO auction process is used to raise the remaining mASSETS in return for Meta. Once sufficient mASSETS have been committed, the auction is finished and traders may collect their bASSET/Meta. Upon successful completion of this second stage, the Meta required for payout to traders is sourced through the following channels:

* A portion of staked Meta will be liquidated;
* Should this not meet demand, Meta will be minted, to a limit, and added to the payout.

This continues until the mASSET's collateralization level equals its outstanding mASSETS.

#### Security Notes

Meta dilution is unlikely to lead to a negative spiral as:

* Meta will continue to derive value from other, uncompromized mASSETS in the mStable protocol.
* The system imposes an upper limit \(through a reserve price\) on the number of Meta that can be minted for the auction, using price data validated by governors.
  * In the event that the auction does not raise the required amount of mASSET to fully re-collateralize, the auction is deemed as failed, no Meta is minted, and auction participants can reclaim their commitment. The affected mASSET is now marked as `failed`, and minting permanently disabled. It now suffers from under-collateralization and is redeemable to this proportionate amount. 

## Example

Assume the USD-pegged mASSET mUSD has a basket with a composition of 20% Stablecoin A, 25% Stablecoin B, 25% Stablecoin C, and 30% Stablecoin D \(which is at maximum weight\). Assume that there are 1.5 million mUSD in circulation.

Assume market prices are as follows:

* Meta $5
* mUSD $0.955 \(max weight is hit, i.e. no arbitrage possible\) 
* Stablecoin A $1.00
* Stablecoin B $1.00
* Stablecoin C $1.00
* Stablecoin D $0.85 

Stablecoin D will likely reach its maximum weight through opportunists using the SWAP and MINT functions to make a profit. Once the maximum weight has been reached, users are only allowed to multi-redeem. 

The governance system can then decide to trigger a re-collateralization event. If this happens, D is auctioned off over a fixed period in exchange for mUSD. Let’s assume that all units of D can be auctioned  at an average best price of 0.82 mUSD per unit of D, meaning all units of D can be exchanged for 450k · 0.82 = 369k mUSD. This 369k mUSD is then burned, reducing the supply of mUSD to 1.131 million and thus changing the price. Specifically, the 1.131 million mUSD is now collateralized with 300k of A + 375k of B + 375k of C = 1.050 million stablecoin units in the basket, with a new weighted average basket price of 1.050M / 1.131M = $0.93.

The de-pegged asset has now been removed from the basket, but it remains under-collateralized.

A portion of staked Meta will then be liquidated and sold. Assume that there are 54,000 Meta staked and 10% are liquidated for re-collateralization. 5,400 Meta is then liquidated and sold for an average price of $4.90, raising $26,460 of mUSD, which is then burned. 

Only if this process fails to cover the full re-collateralization value, Meta will be diluted and sold for mUSD to restore full collateralization and the $1 price. 

In this example, a total of $81k mUSD is needed to be raised to cover the peg loss. Staked MTA covered $26,460 or c.33% of this loss. The remaining $54,540 \(67%\) will be raised through printing and auctioning Meta until the full 81k mUSD is raised. 

If the average price of Meta in the auction is $4.5, 12,120 additional MTA must enter into circulation. If this auction is successful, the $54,540 of mUSD raised through this auction will be burned. This means that the outstanding units of mUSD now match the value of the underlying basket of $1.050M, and the system is again fully backed at $1 per mUSD.  


