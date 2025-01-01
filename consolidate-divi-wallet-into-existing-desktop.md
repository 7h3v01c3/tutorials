# Consolidating Coins from a 12-Word Wallets into a 24-Word Wallet using Divi Wallet Importer and Divi Desktop

## Notes
*Think about this for a moment, read this out loud to yourself: "the app is not a wallet; your words (12 and 24) are what make your wallet."*  
*Hoping this makes you ask questions and empowers you!*

Follow these steps to transfer your DIVI from each 12-word wallet into your main 24-word wallet in Divi Desktop Application. Instructions vary slightly depending on your operating system.

## Before Starting the Recovery Process

1. **Open Your Current Divi Desktop Application**  
   - Ensure you are using your **Divi Desktop Application** with the 24-word wallet that already has coins in it. This will be your primary wallet for consolidating all coins.
   - Generate a receiving address in this wallet and save it in a text file. You’ll use this address to transfer funds from each 12-word wallet.

## Steps for Windows Users

Windows users can use the **Divi Wallet Importer** app to streamline the recovery and consolidation process. [Download Divi Wallet Importer](https://github.com/7h3v01c3/Divi-Wallet-Importer-for-Divi-Desktop-Application/releases/tag/v1.1.0-windows).

### 1. Generate an Address from the 24-Word Wallet
   - Open **Divi Desktop** with your 24-word wallet (the one that already has coins).
   - Generate a receiving address and save it in a text file for reference (you’ll need it in later steps).

### 2. Close Divi Desktop
   - Fully close **Divi Desktop** before proceeding.

### 3. Recover All 12-Word Wallets Using Divi Wallet Importer
   *Follow the Divi Wallet Importer tutorial for any questions.*
   - For each 12-word wallet:
     - Open **Divi Wallet Importer** and import the 12-word phrase to recover the wallet with coins.
     - Unvault any funds if necessary. [How To Manually Unvault](https://www.youtube.com/watch?v=4EBZdnon_Qo)
     - Send the entire balance from this wallet to the Main Address you saved in step 1.
   - After completing the transfer, close **Divi Wallet Importer**.

### 4. Repeat for All 12-Word Wallets
   - Repeat steps 2 and 3 for each 12-word wallet you need to consolidate into your main 24-word wallet.

### 5. Final Recovery of Your 24-Word Wallet
   - Once all transfers are complete, reopen **Divi Desktop**, go to **Settings** > **Security**, and select **Recover**, then choose **Recover from Seed** to re-import your 24-word wallet.

## Steps for Mac Users (Manual Command Line Recovery)

Mac users will need to follow a manual command line recovery process, as the Divi Wallet Importer app is not available for Mac. Please follow the [manual recovery tutorial here](https://github.com/7h3v01c3/tutorials/blob/main/osx_divi_wallet_recovery_in_divi_desktop_application.md) to recover each wallet.

### 1. Generate an Address from the 24-Word Wallet
   - Open **Divi Desktop** with your 24-word wallet (the one that already has coins).
   - Generate a receiving address and save it in a text file for reference.

### 2. Close Divi Desktop
   - Fully close **Divi Desktop** before proceeding.

### 3. Recover Each 12-Word Wallet Using the Command Line
   - For each 12-word wallet:
     - Follow the [manual command line recovery tutorial](https://github.com/7h3v01c3/tutorials/blob/main/osx_divi_wallet_recovery_in_divi_desktop_application.md) to recover the 12-word wallet with coins.
     - Unvault any funds if necessary. [How To Manually Unvault](https://www.youtube.com/watch?v=4EBZdnon_Qo)
     - Once recovered, use the running **Divi Desktop Application** to send the coins from the now-recovered 12-word wallet to the Main Address saved in step 1.
   - After completing the transfer, close **Divi Desktop** and the terminal window.

### 4. Repeat for All 12-Word Wallets
   - Repeat steps 2 and 3 for each 12-word wallet you need to consolidate into your main 24-word wallet.

### 5. Final Recovery of Your 24-Word Wallet
   - Once all transfers are complete, reopen **Divi Desktop**, go to **Settings** > **Security**, and select **Recover**, then choose **Recover from Seed** to re-import your 24-word wallet.

## Completion
After completing these steps, all your funds from the multiple 12-word wallets will be securely transferred to your main 24-word wallet.
