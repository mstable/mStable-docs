---
description: >-
  Swapping is the exchange between one whitelisted bAsset and another at a 1:1
  ratio. Swaps do not affect the number of mAssets in circulation.
---

# Swap

## **How do swaps work?**

The mStable protocol pools pegged crypto assets of similar value. For example, `mUSD` will pool USD pegged crypto assets, `mBTC` will pool tokenised BTC and so on. These pegged crypto assets are selected by Meta Governors and are deemed to have adequate security guarantees against peg loss. This has important implications, one being: any deviation from the peg of an underlying asset is highly likely to be impermanent.

Take USD pegged crypto assets as an example. Say we allow 4 USD pegged crypto assets in the basket. These pegged crypto assets will constantly move slightly from their $1.00 peg, but over time they are very likely to trade around $1.00. For any given period, each pegged crypto asset's price over time will will look something like this:

![https://gblobscdn.gitbook.com/assets%2F-LxR8Ppz-\_JQ7mRRKKgl%2F-M6Rez22Fvu5AII\_Dbol%2F-M6RkL8TeAsvmNwXJA3Q%2FScreen Shot 2020-05-04 at 10.56.27 am.png?alt=media&amp;token=25bbff7c-7047-4a5c-b251-6a47dcc3142d](https://gblobscdn.gitbook.com/assets%2F-LxR8Ppz-_JQ7mRRKKgl%2F-M6Rez22Fvu5AII_Dbol%2F-M6RkL8TeAsvmNwXJA3Q%2FScreen%20Shot%202020-05-04%20at%2010.56.27%20am.png?alt=media&token=25bbff7c-7047-4a5c-b251-6a47dcc3142d)

Price of USDC. _source: Messari_

So far, the peg deviations of major USD pegged crypto assets have been very minor. For that reason, we use Stableswap, a bonding curve formula that is build specifically for trading pegged crypto assets:

$$An^n \sum x\_i + k = Akn^n  + \frac{k^{n+1}}{n^n\prod x\_i}$$

Stableswap has been developed and first implemented by Curve Finance. Here, `x_i` are bAsset reserves, `n` are the number of bAssets \(e.g. 4\), `k` is the total mAsset supply and `A` is a parameter which controls the width of the low-slippage region. The effect of changing `A` can be observed in the figure below:

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4a394a68-1c3f-4d3d-94a1-0eb9c3e08871/Figure\_1.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4a394a68-1c3f-4d3d-94a1-0eb9c3e08871/Figure_1.png)

Therefore, the USD pegged crypto assets can be exchanged with very low slippage. For same peg assets, Stableswap provides highly efficient trading opportunities, and should maximise income for Savers \(see Save\), compared to other bonding curves, such as Uniswap's.

On a technical side note, a `swap` operation which takes bAsset A as input and outputs bAsset B is equivalent to a `mint` with bAsset A and a subsequent `redeem` into bAsset B using the mAsset obtained from minting.

In summary:

* Apart from a trading fee, there is very low slippage trading pegged crypto assets on mStable.
* Since assets are interchangeable, mStable allows minting and redemption of any coin instead of the exact basket \(as long as max weights are not breached\).

## **Arbitrage**

The `swap`function can be used to arbitrage between bAssets when a spread exists. This will occur when the price differential is greater than the swap fee plus its gas \(Ethereum transaction fee\) cost.

### **Swaps at maximum weight**

Swaps that would push a bAsset above its max weight are not allowed, similar to minting and redeeming. Swaps that do not affect the bAsset at maximum weight are unaffected.

### **Swap Fees**

Swap fees are a flat fee, charged in the asset received by a user. These fees are set by Meta Governors.

