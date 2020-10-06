---
description: ➡️ How to mint mAssets like mUSD
---

# MINT

## Minting mAssets

mAssets represent a basket of underlying bAssets and that be minted using any of the bAssets that make up the basket. Developers may mint mAssets using a single bAsset or a combination of more than one.

To mint, interact with the `mAsset` contract. You can discover the deployed addresses for [the mAsset contract here](../deployed-addresses.md). In order to execute the mint:

* choose a bAsset to mint with, or select optimally with [`suggestMintAsset`](mint.md#suggestmintasset)  
* `approve` the `mAsset` address to spend the input asset
* call [`mint`](mint.md#mint) to execute

You may wish to use the [IMasset Interface ](https://github.com/mstable/mStable-contracts/blob/master/contracts/interfaces/IMasset.sol)in your contracts. 

{% hint style="warning" %}
Minting with a bAsset cannot push this asset past its maximum weight.
{% endhint %}

## Masset

### mint

| Input | Output | Estimated gas cost |
| :--- | :--- | :--- |
| bAsset | mAsset | ~140-280k |

```javascript
/**
 * @dev Mint an mAsset (e.g. mUSD) with a single bAsset (e.g. USDC)
 * @param _bAsset        bAsset to mint with
 * @param _bAssetQuanity The amount of bAsset
 * @return massetMinted  The amount of mAsset that was minted
*/
function mint(
    address _basset, 
    uint256 _bassetQuantity
)
    external returns (uint256 massetMinted);
```

### mintTo

| Input | Output | Estimated gas cost |
| :--- | :--- | :--- |
| bAsset | mAsset | ~140-280k |

```javascript
/**
 * @dev Mint an mAsset (e.g. mUSD) with a single bAsset (e.g. USDC)
 * and transfer to a recipient
 * @param _bAsset        bAsset to mint with
 * @param _bAssetQuanity The amount of bAsset
 * @param _recipient The address to transfer minted the minted mAsset to
 * @return massetMinted  The amount of mAsset that was minted
*/        
function mintTo (
    address _basset, 
    uint256 _bassetQuantity, 
    address _recipient
)
    external returns (uint256 massetMinted);

```

### mintMulti

| Input | Output | Estimated gas cost |
| :--- | :--- | :--- |
| bAssets | mAsset | 20k + ~120-250k per bAsset |

```javascript
/**
 * @dev Mint an mAsset (e.g. mUSD) with a multiple bAssets (e.g. USDC & USDT)
 * @param _bAsset        bAssets to mint with
 * @param _bAssetQuanity The amount of bAssets
 * @param _recipient The address to transfer the minted mAsset to
 * @return massetMinted  The amount of mAsset that was minted
*/ 
 
function mintMulti(
    address[] calldata _bAssets, 
    uint256[] calldata _bassetQuantity, 
    address _recipient
)
    external returns (uint256 massetMinted);
```

The mStable Helper contract provides the `suggestMintAsset` function to help integrations verify that a mAsset exists and suggests a bAsset to mint with. The mStable Helper deployed contract addresses may be [discovered here](../deployed-addresses.md).

## MStableHelper

See [Deployed addresses](../deployed-addresses.md) for the current address of the `MStableHelper`.

_NB: This helper is not optimised for gas_

### suggestMintAsset

The mStable Helper contract provides the `suggestMintAsset` function to help integrations select the most optimal bAsset to mint with. The returned bAsset is optimal in terms of price and availability.

```typescript
/**
 * @dev Returns a valid bAsset with which to mint
 * @param _mAsset Masset addr
 * @return valid bool
 * @return string message
 * @return address of bAsset to mint
*/
function suggestMintAsset(
    address _mAsset
)
    external
    view
    returns (
        bool,
        string memory,
        address
    );
```





