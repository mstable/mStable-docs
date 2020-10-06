---
description: "\U0001F3D7️ How to integrate mStable into your smart contracts."
---

# Integrating mStable

## Installation

The mStable protocol contracts are available as an [`npm module`](https://www.npmjs.com/package/@mstable/protocol) that may be included in your projects.

### Using npm

```text
npm install @mstable/protocol --save-dev 
```

### Using yarn

```text
yarn add @mstable/protocol --dev
```

## Integrating mStable

In this following code examples you will learn how to integrate the mStable protocol. This represents a basic integration and more advanced developers may wish to go straight to the nested API docs or the [smart contracts on Github](https://github.com/mstable/mStable-contracts). Deployed contract addresses for Ropsten, Kovan and Mainnet [are listed here](../deployed-addresses.md). 

The examples given here are also available as a single contract in the [mStable example Github repository](https://github.com/mstable/mStable-example). 

{% hint style="info" %}
 mStable smart contracts are compiled against version`0.5.16` of Solidity.
{% endhint %}

**These examples showcase a basic integration using the npm module and are not considered safe.** Your application should build in relevant access control and safety checks.

### 

### Minting mUSD

{% page-ref page="mint.md" %}

Minting takes one or more of the supported tokens and issues mUSD. The following is an example that shows how you can add minting mUSD to a smart contract. **This example assumes** there are some supported stablecoins held on the contract.

Suppose we are minting mUSD with USDC in this example. We first send some USDC to the contract and then call the external `mint` function with the address of the USDC contract and the amount to send. The transaction will return the equivalent amount of mUSD to the contract.

```typescript
pragma solidity ^0.5.16;

import { IMasset } from "@mstable/protocol/contracts/interfaces/IMasset.sol";

...

/**
 * @dev This is a basic example of minting and assumes that some _bAsset 
 * is on the contract. In reality it is likely this would be managed
 * on a per account basis.
 * @param _bAsset           Address of the bAsset (stablecoin) to mint with
 * @param _bAssetQuanity    The amount of bAsset to mint
 *
 */
function mint(
    address _bAsset,
    uint _bAssetQuanity
) external returns (uint massetMinted) {

    // application logic

    IERC20(_bAsset).safeApprove(massetContract, uint256(-1));
    
    return IMasset(massetContract).mint(_bAsset, _bAssetQuanity);
}
```

### Depositing mUSD

{% page-ref page="save.md" %}

Once you have minted mUSD a contract may deposit into the SAVE contract to begin earning yield. This example assumes that mUSD is on the contract. After calling the external `deposit` function, mUSD will be deposited into the SAVE contract and begin earning yield.

```typescript
pragma solidity ^0.5.16;

import { IMasset } from "@mstable/protocol/contracts/interfaces/IMasset.sol";
import { ISavingsContract } from "@mstable/protocol/contracts/interfaces/ISavingsContract.sol";

...


/**
 * @dev This is a basic example of deposits and assumes that some mUSD 
 * is on the contract. In reality it is likely this would be managed
 * on a per account basis
 * @param _amount    The amount of mUSD to deposit
 */
function deposit(
    uint _amount
) external returns (uint256 creditIssued) {

    // application logic
    
    IERC20(massetContract).safeApprove(savingsContract, uint256(-1));
    
    return ISavingsContract(savingsContract).depositSavings(_amount);
}

```

### Withdrawing mUSD

{% page-ref page="save.md" %}

mUSD may be withdrawn from the SAVE contract at any point. This example assumes that the calling contract has deposited into SAVE. Calling the external `withdraw` function returns mUSD from the SAVE contract to the calling contract.

```typescript
pragma solidity ^0.5.16;

import { IMasset } from "@mstable/protocol/contracts/interfaces/IMasset.sol";
import { ISavingsContract } from "@mstable/protocol/contracts/interfaces/ISavingsContract.sol";

...

/**
 * @dev This is a basic example of withdrawing mUSD and assumes that some mUSD 
 * is on the contract. In reality it is likely this would be managed
 * on a per account basis
 * @param _amount    The amount of mUSD to withdraw
 */
function withdraw(
    uint _amount
) external {

    // application logic

    uint256 creditsToRedeem = helper.getSaveRedeemInput(save, _amount);
    ISavingsContract(savingsContract).redeem(creditsToRedeem);
    
    // application logic
}

```

### Redeeming from mUSD

{% page-ref page="redeem.md" %}

Underlying assets may be redeemed from mUSD as the original asset that was deposited or as a mix of any of the underlying assets available in the basket. In this example it is assumed that the contract holds some mUSD and wishes to redeem an underlying stablecoin.

By calling the external `redeem` the caller may redeem an underlying asset. After the transaction completes mUSD will be burned and the underlying asset will be returned to the calling contract.

```typescript
pragma solidity ^0.5.16;

import { IMasset } from "@mstable/protocol/contracts/interfaces/IMasset.sol";

...

/**
 * @dev This is a basic example of redeeming a bAsset and assumes that 
 * some mUSD is on the contract. In reality it is likely this would be managed
 * on a per account basis
 * @param _bAsset           Address of the bAsset (stablecoin) to redeem with
 * @param _bAssetQuanity    The amount of bAsset to mint
 *
 */
function redeem(
    address _bAsset,
    uint _bAssetQuanity
) external returns (uint256 massetRedeemed) {
    return IMasset(massetContract).redeem(_bAsset, _bAssetQuanity);
}
```

