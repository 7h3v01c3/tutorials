

### Migrating Funds from Divi Mobile Wallet to Original Desktop Wallet

#### Overview
The Divi Wallet Mobile, previously provided by Divi Labs, is no longer supported. Users have been migrating their funds from the mobile wallet to the Divi Desktop application, using the **Divi-Wallet-Importer** tool. This tool creates a backup of any existing desktop wallet to ensure user funds are protected, especially when users don't start with an empty wallet.

In this tutorial, we will guide users on how to migrate funds between the **newly imported mobile wallet** and the **original desktop wallet**. The steps also include renaming the wallet files to set the original wallet as the default.

---

### Step 1: Locate Your Original Wallet Backup

1. Press `Windows + R` on your keyboard to open the **Run** dialog.
2. Type `%appdata%` and press **Enter**.
3. Navigate to the following folder:
   ```
   DIVI
   ```
4. Inside the **DIVI** folder, you will see a file named:
   ```
   wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```
   (The date will vary depending on when the backup was created.)
5. Copy the name of this file (e.g., `wallet_backup_2024-xx-xx-xx-xx-xx.dat`) and save it in **Notepad** for later use.

---

### Step 2: Log In to Divi Desktop and Open the Console

1. Open **Divi Desktop** and log in.
2. Open **Debug Console** & Proceed to Step #3
   - If the **Debug Console** isn't visible in the Divi Desktop application, follow these steps:
      - Go to **Settings**.
      - On the **General** tab.
      - Check the box for **Advanced Mode**.
4. After enabling **Advanced Mode**, the **Debug Console** will appear in the top right corner of the Divi Desktop window. Click on it to open the console & proceed to Step #3.

---

### Step 3: Check the Current Wallet

1. Unlock Wallet 
2. Run the following command to check the current wallet you're using:
   ```bash
   getwalletinfo
   ```
3. The output will show that you're in the **default wallet**, which is associated with your 12-word seed phrase:
   ```
   wallet.dat
   ```

---

### Step 4: Load the Original Backup Wallet

1. To access your original backup wallet, carefully run this command. **Replace the date** with the one from the backup file you copied in **Step 1**:
   ```bash
   loadwallet wallet_backup_2024-10-xx-xx-xx-xx.dat
   ```
   **Important**: Do **not** manually type the file name. Use the name you copied to Notepad from **Step 1**, and **paste it using keyboard commands**:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

   **If you mistype the backup wallet name, the system will create a new wallet, causing issues. Double-check your pasted entry!**

2. Wait about 60 seconds for the wallet to load.
3. Once loaded, confirm the correct wallet by running:
   ```bash
   getwalletinfo
   ```
4. The output should display:
   ```
   wallet_backup_2024-10-xx-xx-xx-xx.dat
   ```
   
---

### Step 5: Generate a New Address in the Backup Wallet

1. Use the following command to generate a new address in the original wallet:
   ```bash
   getnewaddress
   ```
2. This will create a new address in your original wallet, which you'll use for migrating your funds.

---

### Step 6: Validate the New Address

1. **Open your notepad** document from earlier, where you saved the name of your backup wallet.
2. In the **Debug Console**, run the following command to validate the new address you generated in the previous step:
   ```bash
   validateaddress <yournewaddress>
   ```
   Replace `<yournewaddress>` with the address from **Step 5**. **Do not manually type it—copy and paste it from your notepad** to avoid mistakes:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

3. Look at the result to confirm that the **`ismine`** field is set to **true**. This confirms the address belongs to your original wallet.
4. **Save this address** in your notepad for future reference by copying it into the same document where you saved the wallet name in **Step 1**.

---

### Step 7: Return to Your Seed Phrase Wallet

1. After you have the new address from your backup wallet, load your 12-word seed phrase wallet again by running:
   ```bash
   loadwallet wallet.dat
   ```

---

### Step 8: Unlock Your Wallet

1. Unlock your seed phrase wallet so you can send funds:
   ```bash
   walletpassphrase <yourpassword> 9999 false
   ```
   Replace `<yourpassword>` with your wallet password.

---

### Step 9: Send Funds to the New Address

1. Send the funds to the address generated from the original wallet:
   ```bash
   sendtoaddress <yournewaddress> <amount>
   ```
   Replace `<yournewaddress>` with the address from Step 5, and `<amount>` with the number of Divi coins to transfer.
2. You will receive a **transaction hash (ID)**. Wait a few minutes for the transaction to confirm.

---

### Step 10: Load the Backup Wallet Again

1. Once the transaction is confirmed, load your backup wallet again:
   ```bash
   loadwallet wallet_backup_2024-10-xx-xx-xx-xx.dat
   ```
2. Run the following command to verify you're in the correct wallet:
   ```bash
   getwalletinfo
   ```

---

### Step 11: Check Your Balance

1. Run this command to check the balance in your original wallet:
   ```bash
   getbalance
   ```
   Confirm that the balance shows the amount you transferred earlier.

---

### Step 12: Rename Wallet Files

1. Close **Divi Desktop** completely.
2. Open **File Explorer** and navigate to:
   ```
   AppData/Roaming/DIVI
   ```
3. Rename the current `wallet.dat` file to:
   ```
   wallet.mobile
   ```
4. Rename your backup wallet file:
   ```
   wallet_backup_2024-10-xx-xx-xx-xx.dat
   ```
   to:
   ```
   wallet.dat
   ```

---

### Step 13: Reopen Divi Desktop

1. Finally, reopen **Divi Desktop**. The application will now load your original wallet, and the funds from the mobile wallet will have been successfully migrated to the default desktop wallet.

---

This tutorial ensures that users can safely move their funds from the Divi Wallet Mobile to the Divi Desktop and make the original wallet their default wallet once again.
