---
description: >-
  The mStable protocol is built with a focus on security, modularity and
  composibility
---

# Architecture

## How does it all work?

The protocol exists as open-access [Smart Contracts ](https://en.wikipedia.org/wiki/Smart_contract)on the [Ethereum](https://ethereum.org) blockchain. The architecture is reasonably straightforward, and consists of a number of modules. Each module provides useful interfaces or support to each other, ultimately facilitating the protection and operation of the mAsset\(s\).

### mAsset interaction

Minting, Swapping and Redeeming in an mAsset is executed by interacting directly with the [mAsset](https://github.com/mstable/mStable-contracts/blob/master/contracts/masset/Masset.sol) contract, with composition managed by the [BasketManager](https://github.com/mstable/mStable-contracts/blob/master/contracts/masset/BasketManager.sol). `bAssets` are integrated with lending protocols \(Aave and Compound\) to generate interest which is accrued in `mAsset` terms. This interaction is performed through a market specific [`Integration`](https://github.com/mstable/mStable-contracts/tree/master/contracts/masset/platform-integrations) contract.

mAssets can be deposited to earn native interest through their respective Savings Contract.

‌Upgrading components, while simply updating an address, should not be taken lightly. mStable employs a multitude of processes to ensure that upgrades go smoothly and the system remains fully robust.

#### Delayed Upgrades 

Module upgrades through the Nexus come in a 2 step process. Step 1 is a successful governance proposal to upgrade the module. In order to confirm this upgrade the system must wait a predefined length of time \(circa 1 week\). This allows users to opt-out of the upgrade, should they no longer wish to hold mAssets and/or Meta. Only after this time has elapsed can the upgrade be locked in.

#### 2-way Handshakes

Each upgrade to Governance will require a two way handshake, in addition to the above Delayed upgrade. This makes absolutely certain that we are passing the baton to the correct address. A two way handshake is basically a confirmation that both parties \(Governance modules\) have opted in to swap permissions, shown by a transaction to propose and consequently accept the new role as Governor. 

#### **Testnet dry runs**

Every system upgrade will first be simulated on the Ethereum testnet to ensure that the resulting state acts as it should.

### How are decisions made?

The decisions are made according to governance proposals by Meta Governors. 

## Where can I see the code?

Accessible on our [Github](https://github.com/mstable) and verified on [Etherscan](https://etherscan.io).

{% hint style="info" %}
Got a question about the code? Check out [who wrote it](../../appendix/about-us.md) or talk to us directly on [Discor​​d](https://discord.gg/7n3m7Tz)
{% endhint %}

