---
description: "\U0001F512 Here are some of the things we do to ensure protocol security"
---

# Security

{% hint style="info" %}
These docs skim the surface - more low level information will be available on launch
{% endhint %}

## Keeping things secure

Ensuring the security and optimisation of a live protocol requires a multi faceted approach. In addition to a macro-level architecture and a [robust governance decentralization](../versioning.md) plan, the micro-[level architecture](security.md#architecture), code formatting, documentation, [testing procedures](security.md#comprehensive-testing-and-auditing-process) and auditing play vital roles in the process.

### Architecture

One of the core principles of our architecture design is the separation of concerns. Many critical modules are immutable, and those modules which are upgradable have an option to be permanently [locked into place](https://app.gitbook.com/@mstable/s/mstable/~/drafts/-M-OWaaE9NNL_1dZ2XvI/protocol/architecture#locking-modules), subject to a governance process.

We use common standardised contracts, for example `MiniMe` or [Open-Zeppelin](https://openzeppelin.com/contracts/) where possible and learn from previous smart contract systems by applying security measures like `ReentrancyGuard` in `Solc v 0.5.x`. 

The Nexus supports the system by providing read access of all modules, as a sort of system registry. This centralises the burden for updates and reduces the chance of a mishap. 

#### Decentralization plan

_See_ [_governance roadmap_](../versioning.md#phases-of-decentralisation) _for more info._

**Deployment**

Deterministic and battle tested deployment scripts play a vital role in ensuring that live contracts are instantiated with and attributed to the correct addresses.

### Supplements

#### Code formatting and readability

We believe that code should be easily understandable and so write with the average reader in mind. Our contracts are formatted for optimal comprehension and supplemented with comprehensive comments.

For example:

* Using descriptive and verbose variable and function names
* Using error messages for every revert, require or assert statement
* Avoid function and variables shadowing
* Remove unused functions, variables and parameters
* Always declare function & variable visibility

#### Helpers

Capitalising on the growing ecosystem of tooling available for writing contracts on Ethereum, we use such tools as:

* Code coverage with [solcover](https://github.com/sc-forks/solidity-coverage)
* Gas reporting and optimisation with [eth-gas-reporter](https://www.npmjs.com/package/eth-gas-reporter)
* Implanting linter, gas and testing rules into a CI task

#### Comprehensive documentation

For internal purposes, auditing and external validation, we write comprehensive docs to describe the system both on a functional and on a technical level.

