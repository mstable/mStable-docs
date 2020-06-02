---
description: "\U0001F4C8 mASSETS within the mStable ecosystem earn interest that is the average of interest earned on composite bASSETS plus platform fees."
---

# SAVE

All mStable assets will be able to earn a native interest rate. This is done by the lending of underlying bASSETS on decentralised lending markets such as Compound or AAVE, combined with mStable's swap fees. 

A smaller portion will be allocated to those [staking](../../meta-rewards-1/staking.md) the mStable protocol token Meta, in return for this token's work in insuring mStable against permanent loss. 

As interest and fees accrue, new mASSETS are minted and sent to the relevant SAVE contract. Users who opt in to receiving interest by depositing a mASSET balance into the contract receive these newly minted mASSETS. This means that mStable assets retain their peg and are therefore both liquidity shares and tokenized assets in their own right.

There will always be a portion of circulating mASSETS being used as a medium of exchange, held offline, or not deposited in the SAVE contract for some other reason. This dynamic, combined with platform fees, should make the interest earned on mASSETS greater than on other yield products. 

### Savings balance increase

When you deposit an mASSET into the SAVE contract, you are internally credited with `Savings Credits` based on the current `exchange rate`. Each time a Saver deposits, the interest is collected from the mASSET and deposited here, increasing the `exchange rate` at the benefit of existing Savers.

`Credits` become increasingly valuable as new deposits are made and the `exchange rate` increases. You can see the function definition from the below solidity snippet. This further explains the relationship between credits, mASSET and the exchange rate.

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

_NB: The notional increase of interest shown on_ [_https://app.mstable.org/save_](https://app.mstable.org/save) _shows balance increasing at 10% APY. This is notional, where the increase in your savings balance will be technically applied at the time of the next `exchange rate` change._

### How is the 24h APY calculated?

**Retrospective** 24 hour APY \(Annual percentage yield\) calculations are shown on the SAVE page of the mStable app. This number is derived from two `exchange rate` changes in the SAVE contract \(see above\) from the **past 24 hours**. 

**Technically?**

Two exchange rates roughly 24 hours apart are taken, and the percentage increase in the rate is calculated \(for example 0.05% in this ~24 hour window\). This rate is then extrapolated to determine what the APY would be if this increase were to happen at this rate for a full year.

The below function calculates the APY, with a compounding interval of the ~24 period:

`apy = ((1 + percentageRateChange)^(compoundIntervalCountPerYear)) - 1`

Where `percentageRateChange` is the % increase in rate over the past 24 hours \(e.g. 0.5%\)  
Where `compoundIntervalCountPerYear` is the number of those 24 hour periods in a year \(based on the actual timestamps of the two data points, so ~365, but **rounded down** to be conservative\)

e.g. `apy = ((1 + 0.0005)^(365))-1 = 19.95%` 

**Who has benefited from this rate?**

Savers who had funds in the SAVE contract for the **full** previous 24 hours.

**Is this indicative of future yield?**

This rate has benefited those Savers over the past 24 hours, but given the short time between the timestamps, is likely to fluctuate on a regular basis. It is **not** a prediction of future savings rates. There are a lot of factors that regularly affect the rate - basket composition \(and thus yield generated from the bASSETS\), SWAP fees and the % of the total mASSETs that are held in the Savings contract.

**Is there more data on SAVE rates?**

We plan to add 7 day APY rates and historical 7 day moving average rates to the mStable dAPP once sufficient data becomes available.   

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

