---
description: >-
  Open reward pool for discovering and reporting vulnerabilities in the mStable
  protocol.
---

# mStable Bug Bounty

Our awesome friends over at **Immunefi.com** are the best place to see a quick breakdown of mStable's bug bounty. Check it out [here](https://immunefi.com/bounty/mstable/).

An **ongoing** bug bounty for the smart contracts of the mStable protocol is now live. mStable intends for hackers to look for smart contract vulnerabilities in our system that can lead to loss of collateral, unfair payouts or locked components. mStable must be as resilient as possible. Please submit a bug and earn a reward of up to US$25,000 ****\(or more in extreme circumstances\)**.** 

_Submissions ****must adhere to the_ [_bug bounty rules**.**_](mstable-bug-bounty.md#rules)_\*\*\*\*_

{% hint style="info" %}
Found a bug? Follow the [responsible disclosure guidelines](mstable-bug-bounty.md#responsible-disclosure) to submit to mStable
{% endhint %}

## **Rewards**

Rewards will be awarded at the sole discretion of the mStableDAO. Quality of the report and reproduction instructions can impact the reward. Rewards are denominated mUSD and will be paid out in mUSD.

The bug bounty program is ongoing and has been running since June 05th, 2020.

NB: Payout amounts increased \(max 25k\) as of July 14th, 2020. 

**The reward will be based on the following severity scheme, based on the** [**OWASP risk rating**](https://owasp.org/www-community/OWASP_Risk_Rating_Methodology) **methodology:**

![](../../.gitbook/assets/screen-shot-2021-01-30-at-1.05.59-pm.png)

## **Reporting**

{% hint style="info" %}
Found a bug? Follow the [responsible disclosure guidelines](mstable-bug-bounty.md#responsible-disclosure) to submit to the team at [Immunefi](https://immunefi.com/bounty/mstable/) or directly to the mStable team.

Failure to following the guidelines will result in a finding being ineligible for any bounties
{% endhint %}

## **Scope**

The bug bounty is applicable to mStable's solidity contract suite, specifically any contracts residing in [**mstable/mStable-contracts/contracts**](https://github.com/mstable/mStable-contracts/tree/master/contracts) ****on "master" branch \(excluding the "z\_mocks" sub-folder\).

{% embed url="https://github.com/mstable/mstable-contracts" %}

### Out of scope

* Any front-end applications or client-side code interacting with the contracts, as well as testing code
* Mismatch of the functionality of the contracts and outdated spec documents

### Areas of interest

* **Loss of collateral or stealing of funds from the mAsset, resulting in it becoming under-collateralised** \(_related: `contracts/masset/*/*`\)_
* Unfair payouts through SAVE, MINT, REDEEM or SWAP functionalities that results in under-collateralised or affected system \(_related: `contracts/masset/**/*`, `contracts/savings/*`\)_
* Manipulating or circumvention of mStable governance mechanism _\(related: `contracts/nexus/Nexus.sol`, `contracts/governance/*`\)_
* Locking or freezing or any of the mStable contracts or inability to upgrade \(_related: `contracts/upgradability/*`_\)
* Ineffective or error prone forge validation mechanisms \(_related: `contracts/masset/forge-validator/*`_\)

## Resources

[mStable Docs - GitBook](https://docs.mstable.org)

\*\*\*\*[**mStable GitHub**](https://github.com/mstable/mstable-contracts)\*\*\*\*

\*\*\*\*[Immunefi](https://immunefi.com/)

## Rules

* Public disclosure of the vulnerability, before explicit consent from mStable to do so, will make the vulnerability ineligible for a bounty
* Attempting to exploit the vulnerability in any public Ethereum network will also make it ineligible for a bounty
* Only unknown vulnerabilities will be awarded a bounty; in case of duplicate reports, the first report will be awarded the bounty
* If you want to add more information to a provided issue, create a new submission giving reference to the initial one
* Rewards will be decided on a case by case basis and the bug bounty program, terms, and conditions are at the sole discretion of mStable
* Submissions need to be related with the Bounty [Scope](mstable-bug-bounty.md#scope). Submissions out of the Bounty Scope won’t be eligible for a reward
* Any interference with the protocol, client or platform services, on purpose or not during the process will make the submission invalid
* Terms and conditions of the bug bounty process may vary over time
* It is mandatory to read and follow the [responsible disclosure policy](mstable-bug-bounty.md#responsible-disclosure) available in the references. Submissions not following the disclosure policy will not be eligible for a reward

### **Exclusions**

While researching, we’d like to ask you to refrain from:

* Denial of service
* Spamming
* Social engineering \(including phishing\) of mStable staff or contractors

### Responsible disclosure

In case you discover a vulnerability, we would like to know about it immediately so we can take steps to address it as quickly as possible.

**If you discover a vulnerability, please do the following**: 

* E-mail your findings to[ security@mstable.org](mailto:security@mstable.org) with the subject "Bug bounty"
* **Do not** take advantage of the vulnerability or problem you have discovered
* **Do not** reveal the problem to others **until** it has been resolved
* **Do not** use attacks on physical security, social engineering, distributed denial of service, spam or applications of third parties;
* **Do** provide sufficient information to reproduce the problem, so we will be able to resolve it as quickly as possible. Complex vulnerabilities may require further explanation so we might ask you for additional information

**We promise the following:** 

* We will respond to your report with a confirmation of receipt, followed by our evaluation of the report and an expected resolution date within 3 business days 
* If you have followed the [instructions above](mstable-bug-bounty.md#rules), we will not take any legal action against you in regard to the report
* We will handle your report with strict confidentiality, and not pass on your personal details to third parties without your permission
* If you so wish we will keep you informed of the progress towards resolving the problem;
* In the public information concerning the problem reported, we will give your name as the discoverer of the problem \(unless you desire otherwise\)
* We offer a reward for every report of a security problem that was not yet known to us. The amount of the reward will be determined based on the severity of the leak, the quality of the report and any additional assistance you provide



{% hint style="info" %}
Questions? Reach out to us on [Discord](https://discord.com/invite/pgCVG7e) or via [Email](mailto:info@mstable.org)
{% endhint %}

