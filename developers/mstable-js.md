---
description: Data processing and validation tools for the mStable Protocol.
---

# mStable-js

### Installation

With Yarn:

```bash
yarn add @mstable/mstable-js
```

Or with npm:

```bash
npm install @mstable/mstable-js
```

### Usage

#### Contracts

**Deployed addresses**

Deployed addresses are available on the [mStable docs](https://docs.mstable.org/developers/deployed-addresses).

**ABIs**

ABIs can be obtained from the [`@mstable/protocol` package](https://www.npmjs.com/package/@mstable/protocol).

**Contracts**

Detailed documentation is available on the [mStable docs](https://docs.mstable.org/) and the Solidity code is available [on GitHub](https://github.com/mstable/mstable-contracts).

#### Data fetching

**Subgraph**

The mStable Protocol Subgraph can be used to fetch data such as mAssets, bAssets, swap transactions, etc.

Available subgraphs:

* [Mainnet](https://thegraph.com/explorer/subgraph/mstable/mstable-protocol)
* [Ropsten](https://thegraph.com/explorer/subgraph/mstable/mstable-protocol-ropsten)
* [Kovan](https://thegraph.com/explorer/subgraph/mstable/mstable-protocol-kovan)

Example query:

```graphql
query {
  masset(id: "0xe2f2a5c287993345a840db3b0845fbc70f5935a5") {
    address: id
    token {
      symbol
      decimals
      totalSupply
    }
  }
}
```

You can use the functions included in mStable JS to get data from the Subgraph, or alternatively, use the queries included in this package \(or write your own\) with your GraphQL client of choice.

Example usage:

```typescript
import { getApolloClient, getAllQueries, Networks } from '@mstable/mstable-js'

const client = getApolloClient(Networks.Mainnet)

const { getMUSD, getMUSDSavingsContract } = getAllQueries(client)

const MUSD = await getMUSD()
// {
//   address: '0x...'
//   bassets: [],
//   // etc.
// }

const MUSDSavingsContract = await getMUSDSavingsContract()
// {
//   address: '0x...'
//   // etc.
// }
```

**Contracts**

Data for mAssets can also be accessed directly from the contracts. This will generally involve more work than using the Subgraph.

Example:

```typescript
import { ethers } from 'ethers'
import MassetABI from '@mstable/protocol/build/contracts/Masset.json'
import BasketManagerABI from '@mstable/protocol/build/contracts/BasketManager.json'
import { CONTRACT_ADDRESSES_MAINNET } from '@mstable/mstable-js'

const provider = new ethers.providers.Web3Provider(window.ethereum)

const MUSD = new ethers.Contract(
  CONTRACT_ADDRESSES_MAINNET.MUSD,
  MassetABI,
  provider,
)

const basketManagerAddress = await MUSD.getBasketManager()

const basketManager = new ethers.Contract(
  basketManagerAddress,
  BasketManagerABI,
)

const basket = await basketManager.getBasket()

const bassets = await basketManager.getBassets()
```

#### Minting mAssets

**Validation**

```typescript
import { parseFixed } from '@ethersproject/bignumber'
import {
  getApolloClient,
  getAllQueries,
  validateMint,
} from '@mstable/mstable-js'

const client = getApolloClient()

const { getMUSD } = getAllQueries(client)

const MUSD = await getMUSD()

{
  const [ok, reason] = validateMint(MUSD, {
    // An object with the bAsset addresses and mint amounts, in the exact bAsset units
    // (USDC is 6 decimals rather than 18)
    '0xDAI': parseFixed('10000', 18),
    '0xUSDC': parseFixed('2000', 6),
  })
  expect(ok).toBeTruthy()
  expect(reason).toBeUndefined()
}

{
  const [ok, reason] = validateMint(MUSD, {
    '0xDAI': parseFixed('960000000', 18),
  })
  expect(ok).toBeFalsy()
  expect(reason).toContain('DAI is overweight')
}
```

**Simulation**

```typescript
import { parseFixed } from '@ethersproject/bignumber'
import {
  getApolloClient,
  getAllQueries,
  simulateMint,
} from '@mstable/mstable-js'

const client = getApolloClient()

const { getMUSD } = getAllQueries(client)

const MUSD = await getMUSD()

const [ok, simulation] = simulateMint(MUSD, {
  '0xDAI': parseFixed('10000', 18),
})
expect(ok).toBeTruthy()
expect(simulation).toMatchObject({
  bassets: { '0xDAI': parseFixed('200000', 18) },
})
```



### Local Development

This project was bootstrapped with [TSDX](https://github.com/jaredpalmer/tsdx).

Below is a list of commands you will probably find useful.

#### `npm start` or `yarn start`

Runs the project in development/watch mode. Your project will be rebuilt upon changes. TSDX has a special logger for you convenience. Error messages are pretty printed and formatted for compatibility VS Code's Problems tab.

Your library will be rebuilt if you make edits.

#### `npm run build` or `yarn build`

Bundles the package to the `dist` folder. The package is optimized and bundled with Rollup into multiple formats \(CommonJS, UMD, and ES Module\).

#### `npm test` or `yarn test`

Runs the test watcher \(Jest\) in an interactive mode. By default, runs tests related to files changed since the last commit.

