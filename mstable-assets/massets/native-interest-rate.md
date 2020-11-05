---
description: "\U0001F4C8 mAssets within the mStable ecosystem earn interest that is the average of interest earned on composite bAssets plus platform fees and other income sources."
---

# SAVE

All mStable assets will earn a native interest rate. This is done by the lending of underlying bAssets on decentralised lending markets such as Compound or AAVE, combined with mStable's swap fees and other sources of income \(such as token liquidations described in [MIP2](https://mips.mstable.org/MIPS/mip-2.html)\). 

As interest and fees accrue, new mAssets are minted and sent to the relevant SAVE contract. Users who opt in to receiving interest by depositing a mAsset balance into the contract receive these newly minted mAssets. This means that mStable assets retain their peg and are therefore both liquidity shares and tokenized assets in their own right.

There will always be a portion of circulating mAssets being used as a medium of exchange, held offline, or not deposited in the SAVE contract for some other reason. This "leveraged" dynamic, combined with platform fees, should make the interest earned on mAssets greater than on other yield products. 

### Savings balance increase

When you deposit a mAsset into the SAVE contract, you are internally credited with `Savings Credits` based on the current `exchange rate`. Each time a Saver deposits, the interest is collected from the mAsset and deposited here, increasing the `exchange rate` at the benefit of existing Savers.

`Credits` become increasingly valuable as new deposits are made and the `exchange rate` increases. You can see the function definition from the below solidity snippet. This further explains the relationship between credits, mAsset and the exchange rate.

```text
/**
 * @dev Deposit the senders savings to the vault, and credit them internally with "credits".
 *      Credit amount is calculated as a ratio of deposit amount and exchange rate:
 *                    credits = underlying / exchangeRate
 *      If automation is enabled, we will first update the internal exchange rate by
 *      collecting any interest generated on the underlying.
 * @param _amount          Units of underlying to deposit into savings vault
 * @return creditsIssued   Units of credits issued internally
 */
function depositSavings(uint256 _amount)
```

### How is the APY displayed?

SAVE shows a historical 7 day moving average APY that has accrued to savers over the last week.

**Who has benefited from this rate?**

Savers who had funds in the SAVE contract for the **full** previous 7 days.

**Is this indicative of future yield?**

This rate has benefited those Savers over the past 7 days, but given the short time between the timestamps, is likely to fluctuate on a regular basis. It is **not** a prediction of future savings rates. There are a lot of factors that regularly affect the rate - basket composition \(and thus yield generated from the bAssets\), SWAP fees and the % of the total mAssets that are held in the Savings contract.

**Is there more data on SAVE rates?**

We have added [platform analytics](https://app.mstable.org/analytics) moving that show average rates over multiple time periods. More data sets will be added to the dAPP once sufficient data becomes available.   

## Lending Platforms

 mStable will launch with a diversity of integrated lending platforms. This reduces the concentration of risk inherent in lending all bAssets on one protocol. Lending platforms can be added or removed and will be decided by [Governance](../functions/governance.md). 

A current list of platforms used by mStable is below:

* [Compound](https://compound.finance/)
* [AAVE](https://aave.com/)

## Platform Fees

The mStable platform can charge fees for users to redeem bAssets and swap bAssets. As these fees accrue, they are allocated to the SAVE contract as another part of the native interest rate.

## Other contributions to APY

There are other sources of value that may also be directed to the SAVE APY. A recent mStable Improvement Proposal \([MIP 2](https://github.com/mstable/MIPs/blob/master/MIPS/mip-2.md)\), for example, directs liquidated COMP tokens to the SAVE contract in order to improve the APY.

## Example

A basket with a total value of 1000 mUSD, comprised of equal parts DAI, USDC, USDT, and TUSD earns interest at the following APY:

* DAI - 5%
* USDC - 4%
* USDT - 3%
* TUSD - 2%

A user deposits 100 mUSD into the SAVE contract, alongside others who have already deposited 400 mUSD. The SAVE contract has a total of 500 mUSD \(50% of mUSD supply\) in it, and over the course of 6 months accrues interest. 

At the end of 6 months, assuming no bASSETS have breached their max weights, the basket is comprised of the following: 256.25 DAI, 255 USDC, 253.75 USDT, and 252.5 TUSD. In total, the basket has accrued 17.5 USD of value in interest at an average rate of 3.5% APY. 

During this period, the platform also collects 10 mUSD in total as fees across swaps and redemption activity. This brings the total USD value accrued in the savings contract to 27.5 USD.

Our user, having contributed one fifth of the total USD in the savings contract over 6 months, earns a corresponding 5.5 mUSD in interest, at an effective APY of 11%.

_NB - This example assumes most of the system to be static over this 6 month term. Realistically, the mStable system is a dynamic one, and returns will be influenced by multiple factors in the system changing on a regular basis._

