---
description: >-
  mStable’s Save is non-custodial savings account that aims to be an accessible,
  reliable and high-yielding place to earn interest.
---

# Save

## Save v2 Audit Report 

{% file src="../../.gitbook/assets/rep-mstable\_18\_01\_2020.pdf" caption="Save v2 Audit Report" %}

## **How does mUSD Save work?**

mStable assets are designed to generate a native interest rate. This is done through the mStable smart contracts programatically depositing bAssets to decentralised lending markets such as Compound or AAVE, combined with mStable's swap fees and other sources of income \(such as token liquidations described in [MIP2](https://mips.mstable.org/MIPS/mip-2.html)\).

As interest and fees accrue, new mAssets are minted and sent to the relevant Save contract. This means that `mUSD` is always 1:1 backed. Users who opt in to receive interest by depositing a mAsset balance into the Save contract receive these newly minted mAssets. The user then receives another token, called `imUSD` which can be redeemed for the original deposit plus any interest earned, at any time.

All savers are given the option to participate in protocol governance. Ever saver has the option of depositing their `imUSD` in the "deposit box", a place where savers can store their `imUSD` and earn `MTA`. As mStable is a collectively governed protocol, it is important that those receive system revenue as yield have a say in protocol governance. The deposit box is designed to incentivise savers to participate in governance and become Meta Governors \(users who participate in protocol governance earn more `MTA`\).

For more information, please refer to these posts:

* [How to Migrate](https://medium.com/mstable/how-to-save-v2-8d102903f03a)
* [mStable launches Save v2](https://medium.com/mstable/mstable-launches-new-composable-version-of-musd-save-982a814e17d0)

## How is the APY displayed?

Save shows a historical 7 day moving average APY that has accrued to savers over the last week.

**Who has benefited from this rate?**

Savers who had funds in the Save contract for the previous 7 days.

**Is this indicative of future yield?**

This rate has benefited those Savers over the past 7 days, but given the short time between the timestamps, is likely to fluctuate on a regular basis. It is **not** a prediction of future savings rates. There are a lot of factors that regularly affect the rate - basket composition \(and thus yield generated from the bAssets\), Swap fees and the percentage of the total mAssets that are held in the Savings contract.

**Is there more data on SAVE rates?**

mStable has added [platform analytics](https://app.mstable.org/analytics) moving that show average rates over multiple time periods. More data sets will be added to the dApp once sufficient data becomes available.   

## **Example**

A basket with a total value of 1000 `mUSD`, comprised of equal parts DAI, USDC, USDT, and TUSD earns interest at the following APY derived from the mStable smart contracts automonously lending deposits onto decentralised lending protocols, currently AAVE and Compound.

* DAI - 5%
* USDC - 4%
* USDT - 3%
* TUSD - 2%

A user deposits 100 `mUSD` into the Save contract, alongside others who have already deposited 400 `mUSD`. The Save contract has a total of 500 `mUSD` \(50% of mUSD supply\) in it, and over the course of 6 months accrues interest.

At the end of 6 months, assuming no bAssets have breached their max weights, the basket is comprised of the following: 256.25 DAI, 255 USDC, 253.75 USDT, and 252.5 TUSD. In total, the basket has accrued 17.5 USD of value in interest at an average rate of 3.5% APY.

During this period, the platform also collects 10 `mUSD` in total as fees across swaps and redemption activity. This brings the total USD value accrued in the savings contract to 27.5 USD.

During this period, the protocol also received $10 worth of Compound tokens from lending on that protocol and $10 worth of AAVE tokens from lending on that protocol. This $20 worth of tokens are autonomously liquidated into `mUSD`. This brings the total USD value accrued in the savings contract to 47.5 USD.

Our user, having contributed one fifth of the total USD in the savings contract over 6 months, earns a corresponding 9.5 `mUSD` in interest.

_NB - This example assumes most of the system to be static over this 6 month term. Realistically, the mStable system is a dynamic one, and returns will be influenced by multiple factors in the system changing on a regular basis, such as users minting and redeeming every day._

