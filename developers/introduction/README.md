---
description: "\U0001F91D Getting to know the mStable protocol"
---

# Introduction

## Resources

### **Contracts**

All contracts are deployed on Mainnet, Ropsten and Kovan. They are open source and available on the GitHub, or as a node package, as specified in the [mStable-protocol page](../integrating-mstable/).

{% page-ref page="../deployed-addresses.md" %}

### Parsing data

See [mStable-js](../mstable-js.md) for more info on ways to retrieve, parse and prepare data for interacting with the core functions.

### Live apps

| Network | App | Subgraph |
| :--- | :--- | :--- |
| Mainnet | [app.mstable.org/](https://app.mstable.org/) | [mstable/mstable-protocol](https://thegraph.com/explorer/subgraph/mstable/mstable-protocol) |
| Ropsten | [app-dot-mstable-ropsten.appspot.com/](http://app-dot-mstable-ropsten.appspot.com/) | [mstable/mstable-protocol-ropsten](https://thegraph.com/explorer/subgraph/mstable/mstable-protocol-ropsten) |
| Kovan | [app-dot-mstable-kovan.appspot.com/](https://app-dot-mstable-kovan.appspot.com/) | [mstable/mstable-protocol-kovan](https://thegraph.com/explorer/subgraph/mstable/mstable-protocol-kovan) |

## Why mStable?

If your application uses `USDT`, `USDC`, `TUSD` or `DAI` you can use mStable to earn a yield for account holders by using the mStable protocol. mUSD represents a basket of underlying stablecoins that is governed and protected by MTA. You can read more about how the protocol works [here](https://docs.mstable.org/mstable-assets/massets). By leveraging mStable, applications can offer account holders a yield on a popular stablecoins while leveraging the additional security of mUSD.

{% hint style="info" %}
mStable contracts have [been independently audited](https://docs.mstable.org/protocol/security#auditing) but you should do your own research and be aware of the risks of using a third-party protocol.
{% endhint %}

Some potential applications that can be created using the mStable protocol are

* Deriving a yield for any application that accepts DAI, USDT, TUSD or USDC
* A no loss lottery \(e.g. PoolTogether\)
* Utilising mStable as part of an trading bot
* A derivative using mStable SAVE or mUSD \(e.g. CHAI\)
* Wrapping MINT/SWAP/REDEEM in something \(e.g. 'accept anything and produce mUSD'\)
* An application that uses mUSD as collateral
* An application that uses MTA as collateral
* An index fund using MTA or mStable, where the SAVE product contributes to the yield
* An interest bearing stablecoin product for custodied stablecoins \(e.g. a CEX\). 

## 

