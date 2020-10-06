---
description: ⬅️ Redeem underlying assets from mAssets (e.g. mUSD)
---

# REDEEM

## Redeem bAssets

mAssets are [minted](mint.md) using one or more of the constituent assets of the basket that makes up a mAsset. For example, mUSD is comprised of USDT, USDC, TUSD and DAI. These underlying assets may be redeemed at any time. 

To redeem, interact with the `mAsset` contract. You can discover the deployed addresses for [the mAsset contract here](../deployed-addresses.md). There are three functions available for redeeming 

* `redeem`
* `redeemTo`
* `redeemMulti` 

You may wish to use the [IMasset Interface ](https://github.com/mstable/mStable-contracts/blob/master/contracts/interfaces/IMasset.sol)in your contracts. 

## Masset

### redeem

| Input arg | Output arg | Estimated gas cost |
| :--- | :--- | :--- |
| bAsset quantities | mAsset Quantity | ~180-340k |

```javascript
 /**
 * @dev Credits the sender with a certain quantity of selected bAsset, in exchange for burning the
 *      relative mAsset quantity from the sender. Sender also incurs a small mAsset fee, if any.
 * @param _bAsset           Address of the bAsset to redeem
 * @param _bAssetQuantity   Units of the bAsset to redeem
 * @return massetRedeemd    Relative number of mAsset units burned to pay for the bAssets
 */
 function redeem(
     address _basset, 
     uint256 _bassetQuantity
 )
     external returns (uint256 massetRedeemed);
```

### redeemTo

| Input arg | Output arg | Estimated gas cost |
| :--- | :--- | :--- |
| bAsset quantities | mAsset Quantity | ~180-340k |

```javascript
/**
 * @dev Credits a recipient with a certain quantity of selected bAsset, in exchange for burning the
 * relative Masset quantity from the sender. Sender also incurs a small fee, if any.
 * @param _bAsset           Address of the bAsset to redeem
 * @param _bAssetQuantity   Units of the bAsset to redeem
 * @param _recipient        Address to credit with withdrawn bAssets
 * @return massetRedeemd    Relative number of mAsset units burned to pay for the bAssets
 */       
  function redeemTo(
      address _basset, 
      uint256 _bassetQuantity, 
      address _recipient
  )
        external returns (uint256 massetRedeemed);

```

### redeemMulti

| Input | Output | Estimated gas cost |
| :--- | :--- | :--- |
|  | bAssets |  |

```javascript
/**
 * @dev Credits a recipient with a certain quantity of selected bAssets, in exchange for burning the
 * relative Masset quantity from the sender. Sender also incurs a small fee, if any.
 * @param _bAssets          Address of the bAssets to redeem
 * @param _bAssetQuantities Units of the bAssets to redeem
 * @param _recipient        Address to credit with withdrawn bAssets
 * @return massetMinted     Relative number of mAsset units burned to pay for the bAssets
*/      
function redeemMulti(
    address[] calldata _bAssets, 
    uint256[] calldata _bassetQuantities, 
    address _recipient
)
    external returns (uint256 massetRedeemed);

```

The mStable Helper contract provides the `getRedeemValidity` function to ascertain whether a redemption is valid. Additionally the mStable Helper contract provides the `suggestRedeemAsset` function to suggest a valid bAsset to redeem. The deployed contract addresses for the mStable Helper contract can be [discovered here](../deployed-addresses.md).

## MStableHelper

See [Deployed addresses](../deployed-addresses.md) for the current address of the `MStableHelper`.

_NB: This helper is not optimised for gas_

### getRedeemValidity

```typescript
/**
 * @dev Determines if a given Redemption is valid
 * @param _mAsset Address of the given mAsset (e.g. mUSD)
 * @param _mAssetQuantity Amount of mAsset to redeem (in mUSD units)
 * @param _outputBasset Desired output bAsset
 * @return valid
 * @return validity reason
 * @return output in bAsset units
 * @return bAssetQuantityArg - required input argument to the 'redeem' call
 */
function getRedeemValidity(
    address _mAsset,
    uint256 _mAssetQuantity,
    address _outputBasset
)
    external
    view
    returns (
        bool,
        string memory,
        uint256 output,
        uint256 bassetQuantityArg
    );
```

### suggestRedeemAsset

```typescript
/**
 * @dev Returns a valid bAsset to redeem
 * @param _mAsset Masset addr
 * @return valid bool
 * @return string message
 * @return address of bAsset to redeem
*/
function suggestRedeemAsset(
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

