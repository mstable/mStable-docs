---
description: "\U0001F310 Interacting with the mStable protocol is permissionless and non-custodial - anyone can build a service to capitalize on the composibility offered through mStable's smart contracts"
---

# Interfacing with mStable

#### **How can I access the mStable protocol?**

The protocol exists as open-access [smart contracts](https://en.wikipedia.org/wiki/Smart_contract) on the [Ethereum](https://ethereum.org/) blockchain, meaning interacting with the protocol is permissionless - anyone can build a dApp layer or communicate directly with the blockchain to access the mStable protocol.

We recommend accessing the contracts through:

The [mStable App](https://docs.mstable.org/mstable-assets/interfacing-with-mstable/app) which is a slim, user focussed web application that allows users to:

* [MINT](https://docs.mstable.org/mstable-assets/massets/minting-and-redemption) and redeem mAssets, allowing you to convert bAssets into mAssets for free
* [SWAP](https://docs.mstable.org/mstable-assets/massets/swapping) between bAssets
* [SAVE](https://docs.mstable.org/mstable-assets/massets/native-interest-rate) mAssets in the mStable Savings Contract
* [EARN](https://docs.mstable.org/mstable-assets/functions) rewards for contributing to the growth of mStable
  * View the reward pools and the history of their allocations

The App is the first product built using the [mStable SDK](https://docs.mstable.org/mstable-assets/interfacing-with-mstable/sdk). Common functionality used here will be dissected, repackaged and re-purposed for the initial integration partners. The dApp is open source.

### A custom dApp or partner DeFi project

dApps or partner DeFi projects wishing to interact with mStable in order to access mAsset and bAsset liquidity, participate in the rewards schemes, capitalise on arbitrage or simply to create an app in their own style can do so. 

Our protocol exists as open-access [Smart Contracts ](https://en.wikipedia.org/wiki/Smart_contract)on the [Ethereum](https://ethereum.org) blockchain. You can simply use a JS tool like [ethers.js ](https://github.com/ethers-io/ethers.js/)to connect your web application to Ethereum.

{% hint style="info" %}
Do you **want to integrate with mStable?** Smart contract integration details are available on the [Developers](../../developers/integrating-mstable/developers.md) page
{% endhint %}

### Communicate directly

It is possible, but not recommended to communicate directly through a Wallet provider \(e.g. [Metamask](https://metamask.io/), [MyCrypto](https://mycrypto.com)\). Doing so means writing your own transaction, which is something you should avoid doing.

