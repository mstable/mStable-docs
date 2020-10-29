---
description: "\U0001F5F3️ Fully decentralized governance is a critical goal for the project - here's our plan."
---

# Governance Roadmap

## Role of governance in mStable

Governors of the mStable protocol can update parameters of the system - for example changing platform fees, [assigning rewards](../meta-rewards-1/introduction/), changing bASSET maximum weights or introducing new mASSETS or bASSETS to the system. It is important that we can fully rely on our governors to make good decisions.  A critical part of the project roadmap is our decentralization plan and an appropriate incentive/penalty system.

Implementing a mature, fully decentralized governance system is impossible to implement overnight, but a realistic plan is critical. 

Capitalizing on the modularity and upgradability of particular system modules, we can theorise an explicit road to decentralization in three distinct phases.

## Phases of decentralization

_For more notes on the purpose of modules picture here, check out the description in_ [_Architecture_](security/architecture.md)_._

## Phase 1

This is the initial implementation of the mStable protocol, and facilitates the core functionality surrounding mASSET usage, while also setting the framework for the transition into later phases. This phase includes the launch of MTA staking V1 in September 2020, and the first steps towards MTA token holder participation via on-chain signalling on mStable's [snapshot page](https://snapshot.page/#/mstable).

### Governance

3/5 [Gnosis Multisig](https://safe.gnosis.io/multisig), primarily controlled by core team members and close affiliates.

## Phase 2

With the Meta token in circulation and being distributed through public rewards and staking returns, mStable will implement its first version of decentralized governance. Phase 2 will be marked by the implementation of the re-collateralization module and MTA staking V2. 

Phase 2 will see the introduction of [Re-collateralization](../mstable-assets/functions/recollateralisation.md) into the system through the `Recol` module, and the introduction of staking V2 into the functionality of the system.

### Governance

[Company Aragon DAO](https://github.com/aragon/dao-templates/tree/master/templates/company) orchestrated by an initial council of Governors - both core team members, advisors, investors, and community members. Instead of merely introducing external governors in the system, there are additional intermediary steps we can take to make the transition easier \(such as limiting vote proposals to a specific group, such as core team and investors at the beginning\).

### Transition Plan

* Deploy a [Company Aragon DAO](https://github.com/aragon/dao-templates/tree/master/templates/company) integrated by an initial council of Governors:
  * The DAO will have a [Token Manager app](https://wiki.aragon.org/archive/dev/apps/token-manager/) using a custom token that will be distributed between the initial governors of the council allowing them to vote
  * There will be a [Staking app](https://github.com/aragon/staking) as a middle layer in charge of ensuring that only Governors that have staked some Meta token are allowed to vote
  * The re-collateralization will use the [Voting app](https://wiki.aragon.org/archive/dev/apps/voting/) built-in in the Aragon DAO
  * The Governor will be the [Agent app](https://hack.aragon.org/docs/guides-use-agent) of the DAO allowing the DAO to call the mStable system when decided by the council
* Transfer the Governor address to the council DAO

## Phase 3

### Governance

At a high level, this phase sees the introduction of a [Company Aragon DAO](https://github.com/aragon/dao-templates/tree/master/templates/company) using the Meta token as the exclusive governance token. The allows us to capitalise on the wide distribution of the Meta token and the maturity of both the protocol and Aragon networks.

### Transition Plan

_There are a number of intermediary steps we can take throughout this deployment, but at a high level, the transition stages are as follows:_

* Deploy a new [company Aragon DAO](https://github.com/aragon/dao-templates/tree/master/templates/company) governed by the community:
  * The DAO will have a [Token Manager app](https://wiki.aragon.org/archive/dev/apps/token-manager/) using the Meta token as the governance token
  * There will be a [Staking app](https://github.com/aragon/staking) as a middle layer in charge of ensuring that only governors that have staked some Meta token are allowed to vote
  * Tweak the Voting app to decide which conditions need to take place in order to be allowed to submit Voting proposals
  * Implementation of delayed upgrades, i.e. 1-2 week implementation buffer before key system parameters are decided upon
  * The re-collateralization will use the new [Voting app](https://wiki.aragon.org/archive/dev/apps/voting/) built-in in the Aragon DAO
  * The Governor will be the [Agent app](https://hack.aragon.org/docs/guides-use-agent) of the DAO allowing the DAO to call the mStable system when decided by the community
* Transfer the Governor address to the community DAO

