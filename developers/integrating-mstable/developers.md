---
description: "\U0001F501 Integration details for interacting with mStable"
---

# SWAP

## Swapping bAssets

mAssets \(e.g. mUSD\) facilitate the **swapping of the underlying bAssets**, on a **1:\(1-fee\)** basis. In the example of mUSD, this means that all bAssets \(**DAI / USDT / TUSD / USDC**\) have open pairs, subject to availability. `bAsset` -&gt; `mAsset` \(e.g. `DAI` -&gt; `mUSD`\) swaps are also supported in the same function and are always 1:1.

In order to execute the trade:

* check that a given pair is valid through [`getSwapOutput`](developers.md#getswapoutput)
* `approve` the `mAsset` address to spend the input asset
* call [`swap`](developers.md#swap) to execute the trade

Swaps relating to a given `mAsset` require interaction directly with that `mAsset` contract - see [deployed addresses](../deployed-addresses.md) for all `mAsset` addresses.

Building an integrating contract or arbitrage bot and want to get the maximum possible swap? Use our [validation helper](developers.md#validationhelper).

### GetSwapOutput

Determines if a SWAP is valid, and returns the expected fee or output.

SWAP is valid if it does not result in the input asset exceeding its maximum weight.

```typescript
/**
 * @param _input        bAsset to deposit
 * @param _output       Asset to receive - bAsset or mAsset(this)
 * @param _quantity     Units of input bAsset to swap
 * @return valid        Bool to signify that swap is current valid
 * @return reason       If swap is invalid, this is the reason
 * @return output       Units of _output asset the trade would return
 */
function getSwapOutput(
    address _input,
    address _output,
    uint256 _quantity
)
    external
    view
    returns (bool, string memory, uint256 output)
```

### Swap

_Important: An integrating contract must first call `approve` on the `_input`bAsset and give permission for the `mAsset` to spend it. `IERC20(_input).approve(mAsset, _quantity)`_

_Note: Gas costs vary from pair to pair given that assets must interact with third party lending platforms_

| Input | Output | Estimated gas cost |
| :--- | :--- | :--- |
| bAsset | mAsset | ~180-300k |
| bAsset | bAsset | ~400-700k |

```typescript
/**
 * @param _input        bAsset to deposit
 * @param _output       Asset to receive - either a bAsset or mAsset(this)
 * @param _quantity     Units of input bAsset to swap
 * @param _recipient    Address to credit output asset
 * @return output       Units of output asset returned
 */
function swap(
    address _input,
    address _output,
    uint256 _quantity,
    address _recipient
)
    external
    nonReentrant
    returns (uint256 output)
```

## MStableHelper

See [Deployed addresses](../deployed-addresses.md) for the current address of the `MStableHelper`.

This helper provides methods to make MINT, SWAP and REDEEM easier to integrate with on chain.

_NB: This helper is not optimised for gas_

### Getting max SWAP available

```typescript
/**
 * @dev Gets the maximum input for a valid swap pair
 * @param _mAsset mAsset address (e.g. mUSD)
 * @param _input Asset to input only bAssets accepted
 * @param _output Either a bAsset or the mAsset
 * @return valid
 * @return validity reason
 * @return max input units (in native decimals)
 * @return how much output this input would produce (in native decimals, after any fee)
 */
function getMaxSwap(
    address _mAsset,
    address _input,
    address _output
)
    external
    view
    returns (
        bool,
        string memory,
        uint256,
        uint256
    )
```



