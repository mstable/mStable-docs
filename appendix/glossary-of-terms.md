---
description: Common terminology used throughout the mStable suite
---

# Glossary of Terms

**Basket** - ****In the context of The mStable Standard, a basket refers to the underlying weighted selection of stablecoins that collateralises an mAsset. Baskets can change over time as MTA holders vote to add, remove, or change the weightings of individual stablecoins within the basket. 

**Basket Asset / bAsset** - ****A Basket Asset is one of the underlying stablecoins present in a Basket. It has a '**Max Weight**' - which is the maximum proportion of the mAssets collateral it is allowed to represent. 

**Forging** - An action of Minting or Redeeming mAssets on-chain through the smart contract system.

**imUSD** - imUSD is a token that represents the yield accruing to mUSD deposited into mStable's Save V2 vault. It is an interest-bearing token that can be redeemed for the underlying mUSD plus any interest earned, at any time. As it is composible, imUSD can also be transferred and used as collateral in other DeFi platforms, making it another useful "money lego" in the broader DeFi ecosystem.

**imUSD Vault** - The imUSD Vault acts as a deposit box where savers holding the imUSD token can also receive MTA rewards in proportion to a deposited amount of imUSD and their vMTA balance. 

**Meta-Stablecoin** - A stablecoin that is collateralised and diversified by an underlying basket of stablecoins. 

**Meta / MTA** - The Meta token \(ticker symbol MTA\) is an ERC-20 utility token on Ethereum, coordinating decentralised governance of mStable assets.

**mStable** - mStable is autonomous and non-custodial stablecoin infrastructure designed to provide decentralized finance platforms and protocols with a base layer collateral protocol on which DeFi applications can be built. mStable is a meta-asset platform that aims to create assets stronger than the sum of their parts.

**mStable Assets / mAssets** - The non-custodial meta-stablecoins created on The mStable Standard, beginning with mUSD and mBTC.

**mUSD** - An mStable Asset pegged to the United States Dollar, and backed by a basket of underlying USD-pegged stablecoins.

**pMTA** - A token that tracks a user's staking reward weight in the Staking v1 implementation of mStable governance. 

**Price oracle** - A service/API which provides real-time price data used by mStable's smart contracts to calculate fees and determine de-pegging events. 

**mStable DAO** - A multi-signer entity that manages all public MTA and mUSD treasury on behalf of the mStable community and Meta Govenors.

**mStable protocolDAO** - A multi-signer entity that executes upgrades to the mStable smart contract suite following Meta Governor approval. 

**Rebalancing** - The mechanism whereby, after a basket change for a mStable Asset, users will receive quantities of the underlying stablecoins such that there is a movement towards the new basket’s composition.

**Save v1** - The old \(now deprecated\) Save contract. No longer receives APY. If you have funds still in this contract please migrate them to Save v2.

**Save v2** - The current Save contract, that allows users to deposit mUSD to earn APY interest. Balances in the Save v2 contracts are represented by imUSD. 

**Stablecoin** - Cryptocurrencies designed to minimise the effect of price volatility, usually via pegging to a particular asset class \(e.g. USD or Gold\).

**vMTA** - A token that tracks a user's voting weight in the Staking v1 implementation of mStable governance. Users receive vMTA when they stake Meta, for an amount that is determined by lockup time and the amount of tokens staked.

