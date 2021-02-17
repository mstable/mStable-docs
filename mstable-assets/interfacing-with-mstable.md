---
description: >-
  Interacting with the mStable protocol is permissionless and non-custodial.
  Anyone can build a service to capitalise on the composibility offered through
  mStable's smart contracts.
---

# Interfacing with mStable

**How can I access the mStable protocol?**

The protocol exists as open-access [smart contracts](https://en.wikipedia.org/wiki/Smart_contract) on the [Ethereum](https://ethereum.org/) blockchain, meaning interacting with the protocol is permissionless - anyone can build a dApp layer or communicate directly with the blockchain to access the mStable protocol.

One such app is the [mStable App](https://docs.mstable.org/mstable-assets/interfacing-with-mstable/app): a slim, user focussed web application that allows users to:

* [MINT](https://docs.mstable.org/mstable-assets/massets/minting-and-redemption) and redeem mAssets, allowing you to convert bAssets into mAssets for free
* [SWAP](https://docs.mstable.org/mstable-assets/massets/swapping) between bAssets
* [SAVE](https://docs.mstable.org/mstable-assets/massets/native-interest-rate) mAssets in the mStable Savings Contract
* [EARN](https://docs.mstable.org/mstable-assets/functions) rewards for contributing to the growth of mStable
  * View the reward pools and the history of their allocations

{% hint style="info" %}
Do you **want to integrate with mStable?** Smart contract integration details are available on the [Developers](../developers/integrating-mstable/developers.md) page
{% endhint %}

### Communicate directly

It is possible, but not recommended to communicate directly through a Wallet provider \(e.g. [Metamask](https://metamask.io/), [MyCrypto](https://mycrypto.com)\). Doing so means writing your own transaction, which is something you should generally avoid doing.

