---
description: >-
  mStable’s Save is non-custodial savings account that aims to be an accessible
  and reliable place to earn interest.
---

# Save

## **How does Save work?**

mStable assets are designed to generate a native interest rate. 

This is done through the mStable smart contracts programatically depositing bAssets to decentralised lending markets such as Compound or AAVE, combined with mStable's swap fees and other sources of income \(such as token liquidations described in [MIP2](https://mips.mstable.org/MIPS/mip-2.html)\).

As interest and fees accrue, new mAssets are minted and sent to the relevant Save contract. This means that the `mAsset`is always fully backed with very little deviation. This deviation occurs when the basket does not have an equal weight distribution, and is due to the bonding curve. The parameters are set in a way so that the deviation is smaller than 1%, 99% of the time. Weight limits ensure that the backing ratio will never drop below 95%.

The one-to-oneness of `mAssets` is in contrast with other Automated Market Maker LP tokens which accrue swap fees implicitly and appreciate in value. Thus, `mAssets` can be used as a pegged crypto assets in its own right, whereas LP tokens cannot. Users who opt in to receive interest by depositing a mAsset balance into the Save contract receive these newly minted mAssets. The user then receives another token, a interest bearing mAsset or `imAssets`, which can be redeemed for the original deposit plus any interest earned, at any time.

All savers are given the option to participate in protocol governance. Every saver has the option of depositing their `imAsset` in the "Vault", a place where savers can store their `imAsset` and earn `MTA`. As mStable is a collectively governed protocol, it is important that those receive system revenue as yield have a say in protocol governance. The vault is designed to incentivise savers to participate in governance and become Meta Governors \(users who participate in protocol governance earn more `MTA`\).

### **Example**

A basket with a total value of 1000 `mUSD`, comprised of equal parts DAI, USDC, USDT, and TUSD earns interest at the following APY derived from the mStable smart contracts autonomously lending deposits onto decentralised lending protocols, currently AAVE and Compound.

* DAI - 5%
* USDC - 4%
* USDT - 3%
* TUSD - 2%

A user deposits 100 `mUSD` into the SAVE contract, alongside others who have already deposited 400 `mUSD`. The SAVE contract has a total of 500 `mUSD` \(50% of mUSD supply\) in it, and over the course of 6 months accrues interest.

At the end of 6 months, assuming no bAssets have breached their max weights, the basket is comprised of the following: 256.25 DAI, 255 USDC, 253.75 USDT, and 252.5 TUSD. In total, the basket has accrued 17.5 USD of value in interest at an average rate of 3.5% APY.

During this period, the platform also collects 10 `mUSD` in total as fees across swaps and redemption activity. This brings the total USD value accrued in the savings contract to 27.5 USD.

During this period, the protocol also received $10 worth of Compound tokens from lending on that protocol and $10 worth of AAVE tokens from lending on that protocol. This $20 worth of tokens are autonomously liquidated into `mUSD`. This brings the total USD value accrued in the savings contract to 47.5 USD.

Our user, having contributed one fifth of the total USD in the savings contract over 6 months, earns a corresponding 9.5 `mUSD` in interest.

_NB - This example assumes most of the system to be static over this 6 month term. Realistically, the mStable system is a dynamic one, and returns will be influenced by multiple factors in the system changing on a regular basis, such as users minting and redeeming every day._

## Using Save

### How do I use Save?

* Head over to [Save](https://app.mstable.org/#/musd/save) on Ethereum or Polygon
* Choose your mAsset to Save with, i.e. mUSD or mBTC
* Deposit supported assets
  * USDT, USDC, DAI and sUSD deposits will be used to [mint](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M_RReTmS-qBH2cBBO6m/mstable-assets/massets/minting-and-redemption) `mUSD`
  * GUSD, BUSD deposits will be used to swap for mUSD through the [Feeder Pools](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M_RReTmS-qBH2cBBO6m/mstable-assets/massets/pools)
  * renBTC, sBTC, WBTC deposits will be used to [mint](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M_RReTmS-qBH2cBBO6m/mstable-assets/massets/minting-and-redemption) `mBTC`
  * TBTC, HBTC deposits will be used to swap for mBTC through the [Feeder Pools](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M_RReTmS-qBH2cBBO6m/mstable-assets/massets/pools)
* Receive `imUSD` or `imBTC` which are yield accruing `mUSD` and `mBTC` and can be transferred and used as collateral in DeFi
* Optionally, stake them into the Vault to [earn MTA rewards](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M_RReTmS-qBH2cBBO6m/mstable-assets/functions)

### Why should I use Save?

Save is one of DeFi's best passive savings account with native and reliable yield, i.e. yield is paid in-kind, automatically.

* mUSD - 10% to 20% APY
* mBTC - 1% to 5% APY

Additionally, yields can be further boosted by staking them in the Savings Vault.

With Save, you do not need to continuously sell rewards and pay expensive gas fees to compound your deposits.

Save deposits are also fully backed by collateral on-chain and redeemable at anytime.

Yield history is fully transparent and trackable on our [dedicated stats page](https://app.mstable.org/#/musd/stats).

### What is the Savings Vault?

* imAssets are now tokenised and can be transferred, e.g. to a third-party protocol for enhanced capital efficiency
* The Savings Vault is one additional avenue, with baked in MTA incentives providing a ‘boost’ for participants who are also actively staking in [Staking](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M_RReTmS-qBH2cBBO6m/mstable-assets/functions/mta-staking)

### How do I choose between imUSD/imBTC and imUSD/imBTC Vault?

* As mentioned above, staking `imUSD` and `imBTC` into the Vault brings MTA incentives to the depositor, with the option to boost by staking MTA
* If left unstaked, the tokenized savings credit can be transferred and used across DeFi, e.g. in [ARCx](https://app.arcx.money) to mint STABLEx

## Save v2 Audit Report 

{% file src="../../.gitbook/assets/rep-mstable\_18\_01\_2020.pdf" caption="Save v2 Audit Report" %}

## \*\*\*\*

