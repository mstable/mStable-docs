---
description: "\U0001F501 Integration details for interacting with mStable"
---

# Developers

## Swapping bAssets

mAssets \(e.g. mUSD\) facilitate the **swapping of the underlying bAssets**, on a **1:\(1-fee\)** basis. In the example of mUSD, this means that all bAssets \(**DAI / USDT / TUSD / USDC**\) have open pairs, subject to availability. `bAsset` -&gt; `mAsset` \(e.g. `DAI` -&gt; `mUSD`\) swaps are also supported in the same function and are always 1:1.

In order to execute the trade:

* check that a given pair is valid through [`getSwapOutput`](developers.md#getswapoutput)
* `approve` the `mAsset` address to spend the input asset
* call [`swap`](developers.md#swap) to execute the trade

Swaps relating to a given `mAsset` require interaction directly with that `mAsset` contract - see [deployed addresses](deployed-addresses.md) for all `mAsset` addresses.

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

_Important: The mAsset must have approval from `msg.sender` to transfer `_input` bAsset in order to execute the swap._

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

