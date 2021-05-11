---
description: >-
  mStable is an autonomous and non-custodial infrastructure for pegged-value
  crypto assets. mStable's first mAsset is mUSD.
---

# mAssets

**Overview**

mStable can support numerous mAssets. Each mAsset is pegged to a unique asset, such as fiat currency \(US Dollar\) or a cryptocurrency like Bitcoin. mAssets are backed by a basket of existing and whitelisted tokenised assets of that same peg, and held by the user.

mAssets are minted/redeemed permissionlessly and on-chain via the mStable smart contracts. Prices for minting and redeeming are set by a predetermined formula, known in the industry as a "bonding curve". While computing the prices, the formula takes bAsset weights into account. Minting prices satisfy the law of demand, that is, the lower the weight of a bAsset \(i.e. the more scarce it is\), the higher the amount of mAsset received per bAsset. The price differentiation provided by the formula allows for arbitrage opportunities, and eventually for bAsset prices, as computed by the formula, to track those of the market.

* **To mint an** `mAsset`, for example, a user sends 1 unit of bAsset and receives 1.0017 `mAsset` in return. This whole process is completed autonomously by mStable's smart contracts and the user interacting with those smart contracts.
* **To redeem,** the user sends an `mAsset` to the contract and can choose which bAsset to receive in return for the swap fee, which is set by Meta Governors. Once the user receives the bAsset\(s\), the mAsset is then burned, i.e. taken out of circulation. This process is completed autonomously by mStable's smart contracts.

Each bAsset will have a minimum and maximum weight that determines its lowest and highest possible weighting in that basket.

A maximum weight is important because it creates an upper-bound to the proportion of a bAsset the mAsset in question is backed by; put differently, it caps a user's exposure to any one pegged crypto asset. Similarly, a minimum weight ensures that the liquidity of a certain bAsset can never decrease below a certain threshold.

Meta Governors determine:

* Parameters of the bonding curve. These parameters dictate how fast the slippage will increase as the basket starts to diverge from an equal weight distribution.
* The maximum and minimum weights of each bAsset.
* Any new bAssets that are to be added should they be deemed secure and stable by the governors. Conversely, a bAsset can be removed should Meta Governors consider it too risky for inclusion in a basket.
* Percentage of the fees incurred during swapping and redemption.

Current mAssets:

* mUSD \(US Dollar\): mAsset consisting of US dollar stablecoins.
* mBTC \(Bitcoin\): mAsset consisting of tokenised bitcoin.

The functionality of other mAssets are the same as mUSD.

Possible future mAssets:

* mETH \(Ether\)
* mGLD \(Gold\)

