---
description: Getting set up on the Ropsten testnet
---

# Ropsten

This walk-through will show you

* How to get Ropsten ETH so you can transact on Ropsten
* How to use the Aave Faucet to get USDT
* How to interact with the mStable dApp to get to know the protocol

You can read more about mStable in the [Getting Started](../../#what-is-mstable) Section

## Testnet walk-through

### Getting Ropsten ETH

mStable is deployed on Ropsten and using Ropsten is recommended for experimenting with the protocol.

It is recommended that you have [MetaMask](https://metamask.io/) setup with some test Ethereum accounts.

You can request Ropsten ETH from the [MetaMask Faucet](https://faucet.metamask.io/). If you are using MetaMask ensure that you have selected the Ropsten network.

After a while you should the transaction will be confirmed and you will see that you have some ETH.

### Getting test pegged assets

To interact with mUSD you will need one or more of the following Stablecoins.

* USDC
* USDT
* TUSD
* DAI

The mStable protocol on Ropsten uses the following pegged assets.

* DAI `0xb5e5d0f8c0cba267cd3d7035d6adc8eba7df7cdd` \(Old Compound\)
* USDC `0x8a9447df1fb47209d36204e6d56767a33bf20f9f` \(Old Compound\)
* TUSD `0xa2ea00df6d8594dbc76b79befe22db9043b8896f` \(Current Aave\)
* USDT `0xB404c51BBC10dcBE948077F18a4B8E553D160084` \(Current Aave\)

TUSD/USDT can be obtained from the [Aave Faucet](https://testnet.aave.com/faucet/) \(pro tip: you can change the data sent in the faucet function to mint more than the default amount\). Compounds Faucet is a bit tricky, which is why an old deployment is used that had sufficient liquidity. If you wish to get DAI/USDC it would be better to first use the Aave faucet, or request `mUSD` from the mStable team via [Discor​​d](https://discord.com/invite/pgCVG7e).

The Tether faucet is known to work so this is recommended. Request some USDT so that you can use the mStable protocol.

### Interacting with the mStable dApp

You can access the testnet version of the mStable protocol using the [mStable dApp ](https://app-dot-mstable-ropsten.appspot.com/)on Ropsten. Please read [Mint](../../mstable-assets/mstable-app/forge/minting-and-redemption/), [Swap](../../mstable-assets/mstable-app/forge/swapping.md), [Save](../../mstable-assets/mstable-app/native-interest-rate.md) and [Earn]() for protocol-specific information.

#### See the [Developers section](get-set-up-on-ropsten.md) to understand how you can build applications on top of the protocol using the smart contract interfaces.

