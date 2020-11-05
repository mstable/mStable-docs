---
description: "\U0001F3D7️ The mStable protocol is built with a focus on security, modularity and composibility"
---

# Architecture

## How does it all work?

The protocol exists as open-access [Smart Contracts ](https://en.wikipedia.org/wiki/Smart_contract)on the [Ethereum](https://ethereum.org) blockchain. The architecture is reasonably straightforward, and consists of a number of modules, some of which are upgradable and some of which are completely immutable. Each module provides useful interfaces or support to each other, ultimately facilitating the protection and operation of the mAsset\(s\).

### mASSET interaction

Minting, Swapping and Redeeming in an mAsset is executed by interacting directly with the [mAsset](https://github.com/mstable/mStable-contracts/blob/master/contracts/masset/Masset.sol) contract, with composition managed by the [BasketManager](https://github.com/mstable/mStable-contracts/blob/master/contracts/masset/BasketManager.sol). `bAssets` are integrated with lending protocols \(initially Aave, Compound\) to generate interest which is accrued in `mAsset` terms. This interaction is performed through a market specific [`Integration`](https://github.com/mstable/mStable-contracts/tree/master/contracts/masset/platform-integrations) contract.

mAssets can be deposited to earn native interest through their respective Savings Contract, just like you would with a savings account.

{% hint style="info" %}
More low level information on the contract architecture coming soon
{% endhint %}

### How do we upgrade components?

Upgrading components, while simply updating an address, should not be taken lightly. In addition to the comprehensive measures put in place by the proposed Governance implementations, we employ a multitude of processes to ensure that upgrades go smoothly and the system remains fully robust.

#### ⏰ Delayed Upgrades 

Module upgrades through the Nexus come in a 2 step process. Step 1 is a successful governance proposal to upgrade the module. In order to confirm this upgrade the system must wait a predefined length of time \(circa 1 week\). This allows users to opt-out of the upgrade, should they no longer wish to hold mAssets and/or Meta. Only after this time has elapsed can the upgrade be locked in.

#### 🤝 2-way Handshakes

Each upgrade to [Governance](../versioning.md) will require a two way handshake, in addition to the above Delayed upgrade. This makes absolutely certain that we are passing the baton to the correct address. A two way handshake is basically a confirmation that both parties \(Governance modules\) have opted in to swap permissions, shown by a transaction to propose and consequently accept the new role as Governor. 

#### ⛷️ **Testnet dry runs**

Every system upgrade will first be simulated on the Ethereum testnet to ensure that the resulting state acts as it should.

### Locking modules 

System modules can be locked for perpetuity, should the current implementation be deemed final. This allows us to gradually transition into a **completely immutable system**, over time.

### How are decisions made?

The decisions are made according to project timelines, and executed by the current governance implementation. See the [Governance roadmap](../versioning.md) for more specific details.



## Where can I see the code?

Accessible on our [Github](https://github.com/mstable) and verified on [Etherscan](https://etherscan.io).

{% hint style="info" %}
Got a question about the code? Check out [who wrote it](../../appendix/about-us.md) or talk to us directly on [Discor​​d](https://discord.gg/7n3m7Tz)
{% endhint %}

