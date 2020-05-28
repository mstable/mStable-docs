---
description: "\U0001F4C8 mASSETS within the mStable ecosystem earn interest that is the average of interest earned on composite bASSETS plus platform fees."
---

# SAVE

Once live, all mStable assets will be able to earn a native interest rate. This is done by the lending of underlying bASSETS on decentralised lending markets such as Compound or AAVE, as well as the swap and redemption fees collected on mStable. 

**The vast majority of this combined amount is allocated to SAVE as interest rate payments**, whilst a smaller portion will be allocated to Meta [staking](../../meta-rewards-1/staking.md), in return for this token's work in insuring mStable against permanent loss. 

As interest and fees accrue, new mASSETS are minted and sent to the relevant SAVE contract. Users who opt in to receiving interest by depositing a mASSET balance into the contract receive these newly minted mASSETS.This means that mStable assets retain their peg and are therefore both liquidity shares and tokenized assets in their own right.

There will always be a portion of circulating mASSETS being used as a medium of exchange, held offline, or not deposited in the SAVE contract for some other reason. This dynamic, combined with platform fees, should make the interest earned on mASSETS greater than on other yield products. 

## Lending Platforms

 mStable will launch with a diversity of integrated lending platforms. This reduces the concentration of risk inherent in lending all bASSETS on one protocol. Lending platforms can be added or removed and will be decided by [Governance](../functions/governance.md). 

A current list of platforms used by mStable is below:

* [Compound](https://compound.finance/)
* [AAVE](https://aave.com/)

## Platform Fees

The mStable platform can charge fees for users to single bASSET redeem and swap bASSETS. As these fee accrue, a portion of them is allocated to the SAVE contract as another part of the native interest amount; the rest will be allocated to Meta holders as payment for insuring mStable. 

## Example

A basket with a total value of 1000 mUSD, comprised of equal parts DAI, USDC, USDT, and TUSD bASSETS earns interest at the following APY:

* DAI - 5%
* USDC - 4%
* USDT - 3%
* TUSD - 2%

A user deposits 100 mUSD into the SAVE contract, alongside others who have already deposited 400 mUSD. The SAVE contract has a total of 500 mUSD \(50% of mUSD supply\) in it, and over the course of 6 months accrues interest. 

At the end of 6 months, assuming no bASSETS have breached their max weights, the basket is comprised of the following: 256.25 DAI, 255 USDC, 253.75 USDT, and 252.5 TUSD. In total, the basket has accrued 17.5 USD of value in interest at an average rate of 3.5% APY. 

During this period, the platform also collects 10 mUSD in total as fees across swaps and redemption activity. This brings the total USD value accrued in the savings contract to 27.5 USD.

Our user, having contributed one fifth of the total USD in the savings contract over 6 months, earns a corresponding 5.5 mUSD in interest, at an effective APY of 11%.

_NB - This example assumes most of the system to be static over this 6 month term. Realistically, the mStable system is a dynamic one, and returns will be influenced by multiple factors in the system changing on a regular basis. It also omits the portion of interest and platform fees that are earned in staking rewards by governors when this launched._  

