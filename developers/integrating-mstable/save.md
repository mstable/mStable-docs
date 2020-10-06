---
description: "\U0001F4C8 Earning yield on minted mAssets"
---

# SAVE

## Deposit and redeem mAssets

After [minting](mint.md), mAssets \(e.g. mUSD\) may be deposited into the relevant SAVE contract to earn a yield. Once deposited, mAsset is held on the SAVE contract but may be redeemed at any time. 

To deposit and redeem, interact with the `SAVE` contract. You can discover the deployed addresses for [the SAVE contract here](../deployed-addresses.md). There are two functions available depositing and redeeming

* `depositSavings`
* `redeem` 

You may wish to use the [ISavingsContract Interface](https://github.com/mstable/mStable-contracts/blob/master/contracts/interfaces/ISavingsContract.sol) in your contracts. 

{% hint style="info" %}
An integrating contract must first call`approve`on the mAsset and give permission for the SAVE contract to spend.
{% endhint %}

## SavingsContract

### depositSavings

| Input | Output | Estimated gas cost |
| :--- | :--- | :--- |
| mAsset | savingsCredit | ~280-350k |

```javascript
/**
 * @dev Deposit mAsset into the SAVE Conract to earn yield
 * @param _amount          Units of underlying bAsset (e.g mUSD) to deposit
 * @return creditsIssued   Units of credits issued internally
*/
function depositSavings(
    uint256 _amount
) 
    external returns (uint256 creditsIssued);
```

### redeem

Note - The redeem call takes the credit amount. You should use the [getSaveRedeemInput](save.md#getsaveredeeminput) function on the mStable Helper to get the required credits.

| Input | Output | Estimated gas cost |
| :--- | :--- | :--- |
| mAsset | savingsCredit | ~70-100k |

```javascript
/**
 * @dev Redeem mAsset from the SAVE contract
 * @param _credits         Amount of credits to redeem
 * @return massetReturned  Units of underlying mAsset paid out
*/        
function redeem(
    uint256 _amount
) 
    external returns (uint256 massetReturned);

```

The mStable Helper contract provides the `getSaveBalance` function to get a users SAVE balance in mAsset terms. Additionally the mStable Helper contract provides the `getSaveRedeemInput` function to get the amount of credits to withdraw for a certain amount of mAsset. The deployed contract addresses for the mStable Helper contract can be [discovered here](../deployed-addresses.md).

## MStableHelper

See [Deployed addresses](../deployed-addresses.md) for the current address of the `MStableHelper`.

### getSaveBalance

```typescript
/**
 * @dev Gets the users savings balance in mAsset terms
 * @param _save SAVE contract address
 * @param _user Address of the user
 * @return balance in mAsset units
 */
function getSaveBalance(
    ISavingsContract _save,
    address _user
)
    external
    view
    returns (
        uint256
    );
```

### getSaveRedeemInput

```typescript
/**
 * @dev Returns the 'credit' units required to withdraw a certain
 * amount of Masset from the SAVE contract
 * @param _save SAVE contract address
 * @param _amount Amount of mAsset to redeem from SAVE
 * @return input for the redeem function (ie. credit units to redeem)
 */
function getSaveRedeemInput(
    ISavingsContract _save,
    uint256 _amount
)
    external
    view
    returns (
        uint256
    );
```

