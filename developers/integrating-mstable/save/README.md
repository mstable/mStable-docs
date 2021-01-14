---
description: "\U0001F4C8 Earning yield on minted mAssets"
---

# SAVE

## Deposit and redeem mAssets from SAVE

mAssets \(e.g. `mUSD`\) may be deposited into the relevant Savings Contract to earn a yield, in return a redeemable `imAsset` is issued, representing the interest accruing mAsset. Once deposited, mAsset is held on the SAVE contract but may be redeemed at any time by burning the `imAsset` \(e.g. `imUSD`\) token.

The `imAsset` conforms to the **ERC20** standard.

The starting exchange rate between `imAsset` and mAsset is 10:1, with the `imAsset` gradually increasing in value over time as interest is accrued.

| Function | Estimated gas costs |
| :--- | :--- |
| `depositSavings(uint256 _underlying)` | ~150k |
| `depositSavings(uint256 _underlying, address _beneficiary)` | ~150k |
| `redeemCredits(uint256 _credits)` | ~150k |
| `redeemUnderlying(uint256 _underlying)` | ~150k |

## Savings Contract Interface

### Deposit

Deposit `mAsset` and receive an ERC20 `imAsset` in return.

```typescript
/**
 * @dev Deposit the senders savings to the vault, and credit them internally with "credits".
 *      Credit amount is calculated as a ratio of deposit amount and exchange rate:
 *                    credits = underlying / exchangeRate
 *      We will first update the internal exchange rate by collecting any interest generated on the underlying.
 * @param _underlying      Units of underlying to deposit into savings vault
 * @return creditsIssued   Units of credits (imUSD) issued
 */
function depositSavings(uint256 _underlying)
    external
    returns (uint256 creditsIssued)
```

```typescript
/**
 * @dev Deposit the senders savings to the vault, and credit them internally with "credits".
 *      Credit amount is calculated as a ratio of deposit amount and exchange rate:
 *                    credits = underlying / exchangeRate
 *      We will first update the internal exchange rate by collecting any interest generated on the underlying.
 * @param _underlying      Units of underlying to deposit into savings vault
 * @param _beneficiary     Immediately transfer the imUSD token to this beneficiary address
 * @return creditsIssued   Units of credits (imUSD) issued
 */
function depositSavings(uint256 _underlying, address _beneficiary)
    external
    returns (uint256 creditsIssued)
```

```typescript

/**
 * @dev During a migration period, allow savers to deposit underlying here before the interest has been redirected
 * @param _underlying      Units of underlying to deposit into savings vault
 * @param _beneficiary     Immediately transfer the imUSD token to this beneficiary address
 * @return creditsIssued   Units of credits (imUSD) issued
 */
function preDeposit(uint256 _underlying, address _beneficiary)
    external
    returns (uint256 creditsIssued)
```



### Redeem

Convert `imAsset` back into `mAsset`, by specifying either amount.

```typescript
/**
 * @dev Redeem specific number of the senders "credits" in exchange for underlying.
 *      Payout amount is calculated as a ratio of credits and exchange rate:
 *                    payout = credits * exchangeRate
 * @param _credits         Amount of credits to redeem
 * @return massetReturned  Units of underlying mAsset paid out
 */
function redeemCredits(uint256 _credits)
    external
    returns (uint256 massetReturned)
```

```typescript
/**
 * @dev Redeem credits into a specific amount of underlying.
 *      Credits needed to burn is calculated using:
 *                    credits = underlying / exchangeRate
 * @param _underlying     Amount of underlying to redeem
 * @return creditsBurned  Units of credits burned from sender
 */
function redeemUnderlying(uint256 _underlying)
    external
    returns (uint256 creditsBurned)
```

### 

### Checking balance

Each credit gradually accrues value as the system exchange rate goes up. This can be tracked by calling `balanceOfUnderlying`

```typescript
/**
 * @dev Returns the underlying balance of a given user
 * @param _user     Address of the user to check
 * @return balance  Units of underlying owned by the user
 */
function balanceOfUnderlying(address _user)
   external
   view
   returns (uint256 balance);
```

```typescript
/**
 * @dev Returns the credit balance (e.g. imAsset balance) of a given user
 * @param _user     Address of the user to check
 * @return balance  Units of imAsset owned by the user
 */
function balanceOf(address _user)
   external
   view
   returns (uint256 balance);
```

#### **Unit conversion**

```typescript
/**
 * @dev Converts a given underlying amount into credits
 * @param _underlying  Units of underlying
 * @return credits     Credit units (a.k.a imUSD)
 */
function underlyingToCredits(uint256 _underlying)
   external
   view
   returns (uint256 credits);
```

```typescript
/**
 * @dev Converts a given credit amount into underlying
 * @param _credits  Units of credits
 * @return amount   Corresponding underlying amount
 */
function creditsToUnderlying(uint256 _credits)
    external
    view
    returns (uint256 amount);
```













