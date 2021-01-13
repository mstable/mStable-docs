---
description: >-
  Swapping is the exchange between one whitelisted bAsset and another at a 1:1
  ratio. Swaps do not affect the number of mAssets in circulation.
---

# SWAP

## **How do swaps work?**

The mStable protocol pools stablecoins of similar value. For example, `mUSD` will pool USD stablecoins, `mBTC` would pool tokenised BTC and so on. These stablecoins are selected by Meta Governors and are deemed to have adequate security guarantees against peg loss. This has important implications, one being: any deviation from the peg of an underlying asset is highly likely to be impermanent.

Take USD stablecoins as an example. Say we allow 4 USD stablecoins in the basket. These stablecoins will constantly move slightly from their $1.00 peg, but over time they are very likely to trade around $1.00. For any given period, each stablecoin's price over time will will look something like this:

![https://gblobscdn.gitbook.com/assets%2F-LxR8Ppz-\_JQ7mRRKKgl%2F-M6Rez22Fvu5AII\_Dbol%2F-M6RkL8TeAsvmNwXJA3Q%2FScreen Shot 2020-05-04 at 10.56.27 am.png?alt=media&amp;token=25bbff7c-7047-4a5c-b251-6a47dcc3142d](https://gblobscdn.gitbook.com/assets%2F-LxR8Ppz-_JQ7mRRKKgl%2F-M6Rez22Fvu5AII_Dbol%2F-M6RkL8TeAsvmNwXJA3Q%2FScreen%20Shot%202020-05-04%20at%2010.56.27%20am.png?alt=media&token=25bbff7c-7047-4a5c-b251-6a47dcc3142d)

Price of USDC. _source: Messari_

So far, the peg deviations of major USD stablecoins have been impermanent. Since these losses are impermanent, we can allow our bonding curve to be constant, namely:

_q\(x\)+q\(y\)=k_

Therefore, the USD stablecoins can be exchanged 1 for 1, a constant bonding curve. The slope is constant, meaning price is independent of supplies of coin x and coin y.

In summary:

* Apart from a trading fee, there is zero slippage trading stablecoins and tokenised assets on mStable. Price remains the same independent of assets in the basket.
* Since assets are interchangeable, mStable allows minting and redemption of any coin instead of the exact basket \(as long as max weights are not breached\).

## **Arbitrage**

The `swap`function can be used to arbitrage between bAssets when a spread exists. This will occur when:

* When the price differential is greater than the swap fee plus its gas \(Ethereum transation fee\) cost.
* There is excess room in the system between a bAsset and its max weights to allow mStable to take on more of that undervalued asset.

### **Swaps at maximum weight**

Swaps that would push a bAsset above its max weight are not allowed. Swaps that do not affect the bAsset at maximum weight are unaffected.

### **Swap Fees**

Swap fees are a flat fee, charged in the asset received by a user. These fees are set by Meta Governors.

