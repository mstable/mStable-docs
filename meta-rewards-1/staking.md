---
description: >-
  ⛏ Meta Governors earn an income to compensate them for their work,
  responsibility and risk
---

# Staking

## Why?

To incentivise sound decision making, Meta Governors are paid when mStable grows securely and are partially liquidated as part of [Recollateralisation](../mstable-assets/functions/recollateralisation.md). 

To participate as a Meta Governor, holders must stake their MTA. MTA holders who choose to stake their MTA would be partially liquidated in the event of a [Recollateralisation](../mstable-assets/functions/recollateralisation.md). In return, those who stake are rewarded for their risk in fees and interest that the platform collects.  

This staking reward will be a floating value, and will change dependent on how much MTA is staked versus the fees and interest the platform receives. We expect the staking return to increase as the mStable platform matures, with return approaching an equilibrium that reflects the perceived risk of a re-collateralisation event taking place, opportunity cost of that Meta, plus some liquidity premium. 

## Example

Our user has 1000 Meta that they wish to stake. As soon as this user stakes their Meta, she begins to earn rewards from fees and interest on the platform. Her staked Meta entitles the user to a share of fees equal to the portion of Meta staked relative to the total amount staked. Our user stakes her 1000 Meta over a month, with 1 million Meta staked in the total system, during a month where 50,000 mUSD in fees and interest are collected in the mStable ecosystem that are allocated to Meta Stakers. She calculates her return with the following formula: 

$$
return = s/S ⋅ Fm
$$

where:

* s = amount of Meta staked by user
* S = Total amount of Meta staked in the system
* Fm = Income from fees and interest collected over the month directed to Meta \(mUSD\)

Substituting our values in, we can calculate our user's staking return:

$$
return = 10,000/1,000,000 ⋅ 50,000 = 500
$$

Our user staked 10,000 Meta for a month, and received a 500 mUSD monthly return for doing so.

* Cost: Gas, opportunity cost of Meta
* Risk: partial liquidation in event of a bASSET losing its peg
* Reward: staking return

_It is worth noting that since the amount of Meta staked in the system changes, return will be dynamic, changing in response to Meta being staked and withdrawn. Our example assumes a fixed amount of total Meta staked in the system for simplicity._



