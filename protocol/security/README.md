---
description: "\U0001F512 Here are some of the things we do to ensure protocol security"
---

# Security

## Keeping things secure

Ensuring the security and optimisation of a live protocol requires a multi faceted approach. In addition to a macro-level architecture and a [robust governance decentralization](../versioning.md) plan, the micro-level architecture, code formatting, documentation, [testing procedures](./#testing) and auditing play vital roles in the process.

## Bug bounty

Open reward pool for discovering and reporting vulnerabilities in the mStable protocol.

{% page-ref page="mstable-bug-bounty.md" %}

## Auditing

Audit completed by [Consensys Diligence](https://diligence.consensys.net/) - report available [here](https://diligence.consensys.net/audits/2020/07/mstable-1.1/) or PDF below.

{% file src="../../.gitbook/assets/mstable-audit-2020-07.pdf" %}

Initial audit performed by Bramah Systems.

{% file src="../../.gitbook/assets/mstable-audit-bramah-systems.pdf" caption="Audit report" %}

## Testing

{% hint style="info" %}
The [mStable-contracts](https://github.com/mstable/mstable-contracts) repository underwent full unit and integration testing. See the report on [Coveralls here](https://coveralls.io/github/mstable/mStable-contracts)
{% endhint %}

mStable contracts are tested with both integration results and invariants in mind.

Tests are written in Typescript, using [Typechain](https://github.com/ethereum-ts/TypeChain) to generate typings for all contracts. Tests are executed using `truffle` and `ganache-cli`.

**Ganache-fork**

mStable-contracts test suite is built to support execution on a [mainnet fork](https://medium.com/ethereum-grid/forking-ethereum-mainnet-mint-your-own-dai-d8b62a82b3f7) of ganache. This allows tests to be ran using all mainnet dependencies \(bAssets, lending protocols\). To do this, certain mainnet accounts need to be unlocked to allows tx to be sent from that origin.

Running tests on a fork of mainnet allows us to validate that all connections act as assumed before performing a real mainnet deployment.

**Coverage**

[Solidity-coverage](https://github.com/sc-forks/solidity-coverage) is used to run coverage analysis on test suite.

This produces reports that are visible in the `/coverage` folder, and navigatable/uploadable. Ultimately they are used as a reference that there is some sort of adequate cover, although they will not be a source of truth for a robust test framework. Reports publically available on [coveralls](https://coveralls.io/github/mstable/mStable-contracts).

### Static analysis

All contracts have undergone static analysis using [Slither](https://github.com/crytic/slither) and [Securify](https://securify.chainsecurity.com/), with resulting outputs either fixed or dismissed.

## Architecture & Code

One of the core principles of our architecture design is the separation of concerns. Many critical modules are immutable, and those modules which are upgradable have an option to be permanently [locked into place](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M-OWaaE9NNL_1dZ2XvI/protocol/architecture#locking-modules), subject to a governance process. Contracts that implement Open-Zeppelin's Upgradable Proxies are governed and upgraded by a DelayedProxyAdmin, via mStable governance.

We use common standardised contracts, for example `MiniMe` or [Open-Zeppelin](https://openzeppelin.com/contracts/) where possible and learn from previous smart contract systems by applying security measures like `ReentrancyGuard` in `Solc v 0.5.x`. 

The Nexus supports the system by providing read access of all modules, as a sort of system registry. This centralises the burden for updates and reduces the chance of a mishap. 

### Decentralization plan

_See_ [_governance roadmap_](../versioning.md#phases-of-decentralisation) _for more info._

### **Deployment**

Deterministic and battle tested deployment scripts play a vital role in ensuring that live contracts are instantiated with and attributed to the correct addresses.

### Code formatting and readability

We believe that code should be easily understandable and so write with the average reader in mind. Our contracts are formatted for optimal comprehension and supplemented with comprehensive comments.

For example:

* Using descriptive and verbose variable and function names
* Using error messages for every revert, require or assert statement
* Avoid function and variables shadowing
* Remove unused functions, variables and parameters
* Always declare function & variable visibility

### Helpers

Capitalising on the growing ecosystem of tooling available for writing contracts on Ethereum, we use such tools as:

* Code coverage with [solcover](https://github.com/sc-forks/solidity-coverage)
* Gas reporting and optimisation with [eth-gas-reporter](https://www.npmjs.com/package/eth-gas-reporter)
* Implanting linter, gas and testing rules into a CI task

{% hint style="info" %}
Got a question or concern about security? Email directly to [security@mstable.org](mailto:security@mstable.org)
{% endhint %}

