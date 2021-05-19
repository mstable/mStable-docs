# Guide to interacting with mStable

### Connecting to mStable app on Polygon

* Navigate to the [app](https://app.mstable.org/)
* Connect your wallet and authorise access
* Switch network from Ethereum to Polygon using the switcher on the top-right

### Minting mAssets \(e.g. mUSD\)

* Head over to [Forge](https://app.mstable.org/#/musd/forge/mint)
* Click on the Mint tab
* Select the mAsset to mint
* Select the asset to mint from \(e.g. sUSD, USDT, USDC, DAI, BUSD, GUSD\)
* Enter the amount to mint and click Mint
* Approve the smart contract to spend your tokens if it's your first time interacting with the contract
* Send the transactio
* Click Mint again
* Send the transaction
* Verify the mAsset minted in your wallet

### Depositing mAssets into Save

* Head over to [Save](https://app.mstable.org/#/musd/save)
* Head down to Deposit
* Select the input asset to deposit \(e.g. mUSD, USDT, USDC, DAI, BUSD, GUSD\)
  * When selecting non mAssets, mStable will first **Mint** the mAsset
* Click **Save** \(if depositing via mAssets\) or **Mint and Save**
* Approve the contract to spend your tokens if it's your first time interacting with the contract
* Click Save or Mint and Save again
* Send the transaction
* Done! You have deposited into Save
* Your Savings is tokenized in the form of imAssets \(e.g. imUSD, imBTC\) which increase in value over time

### Withdrawing from Save

* Head over to [Save](https://app.mstable.org/#/musd/save)
* Head down to Redeem
* Select the amount of imAssets to withdraw
* Click Withdraw
* Send the transaction

### Redeeming mAssets \(e.g. mUSD\) for underlying assets

* Head over to [Forge](https://app.mstable.org/#/musd/forge/mint)
* Click on the Redeem tab
* Select the mAsset to redeem
* Select amount to redeem
* Select output asset \(e.g. USDC, USDT\) or switch to multi-asset redemption to redeem into multiple underlying assets
* Click Redeem

_Fees for redemption are 0.03% for multiple asset redeem and 0.06% for single asset redeem and goes to Save deposits_

### Swapping between assets

mStable also has an underlying AMM that allows underlying assets in its basket to be swapped

* Head over to [Forge](https://app.mstable.org/#/musd/forge/swap)
* Click on the Swap tab
* Choose the input and output currencies
* Enter the amount to swap
* Verify the exchange rate, swap fees, and penalty
* Configure advanced settings such as max slippage if needed
* Click Swap
* Approve the contract to spend your tokens if it's your first time
* Click Swap again

_Fees for swaps are currently 0.06% and goes to Save deposits_

### Tracking balances

There are a couple of ways to track your balances. Since mAssets and imAssets are all ERC-20 tokens in their own right, you can track them like how you'd track any other ERC-20 token on the blockchain.

On mStable:

* On the Account modal
  * Click on your address on the top navbar
  * Scroll to find a consolidated view of your balances including mAssets, imAssets and bAssets
* On the Save homepage
  * If you have deposited in Save, you can find your Save balance in the Save homepage

On external platforms like Zapper.Fi, Zerion and DeBank.

