### Migrating Funds Imported from Divi Wallet Mobile (12-word seeds) to the Original Divi Desktop Wallet (24-word seeds)

---

### Overview

If you imported funds using the Divi Wallet Importer and didn’t use a newly installed Divi Desktop Application, you may have funds in two wallets: the recently imported Divi Wallet Mobile and your original Divi Desktop wallet file that was preserved. This manual tutorial will help you migrate to a single wallet, specifically your original Divi Desktop wallet with 24 words. You’ll send all the funds to an address associated with the original wallet, then we will reset the original Divi Desktop wallet as the default after confirming your balance update.

---

### Step 1: Prepare and Save Important Information

1. **Open a Text Editor**:
   - **Windows**: Press `Alt + Space`, type `notepad`, and hit **Enter**.
   - **macOS**: Press `CMD + Space`, type `TextEdit`, and hit **Enter**.
   
2. **Create and Save the Document**:
   - Name the file something meaningful, like `migration.txt`, and save it on your **Desktop** for easy access.
   
Here is the revised **Step 3** with your changes incorporated:

---

### Step 2: Locate Your Original Wallet Backup

1. **Press** `Windows + R` on your keyboard, type `%appdata%`, and hit **Enter**.
   
2. **Open the Divi folder**:
   ```
   DIVI
   ```
   
3. **Look for a file named**:
   ```
   wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```
   
4. **Copy the name of this file** (e.g., `wallet_backup_2024-xx-xx-xx-xx-xx.dat`) and **paste it into your `migration.txt` document**.

   **It is imperative that you copy it perfectly** to avoid errors later in the process.

5. **Save the file** using `Ctrl + S` on Windows or `Cmd + S` on macOS.

---

### Step 3: Log In to Divi Desktop and Enable Debug Console

1. **Open Divi Desktop** and log in.
2. Open **Debug Console** 
   - If Debug Console isnt visible
     - **Enable Debug Console**:
        - Go to **Settings**.
        - On the **General** tab, check the box for **Advanced Mode**.
     - Once **Advanced Mode** is enabled, the **Debug Console** will be visible at the top. Click it to open the console.

---

### Step 4: Verify Current Wallet

1. **Unlock your wallet** if necessary.
   
2. Run the following command in Debug Console to check the current wallet you're using:
   ```bash
   getwalletinfo
   ```
   
3. The output will show that your "active_wallet" is wallet.dat which the default when Divi Desktop Application starts, which after using Divi Wallet Importer is the 12-word seed phrase wallet:
   ```bash
    "active_wallet" : "wallet.dat"
   ```

---

### Step 5: Load the Original Backup Wallet

1. To access your original backup wallet, in Debug Console run the following command, by entering loadwallet and pasting in your backed up wallet file name.
   ```bash
   loadwallet wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```
   **Important**: Do **not** manually type the file name. **Copy** the name from your **migration.txt** document and **paste** it using keyboard commands:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

   **Spelling errors will create a new wallet, causing issues. Double-check your pasted entry** to avoid mistakes.

2. Wait about 60 seconds for the wallet to load.

3. In Debug Console run the following command to confirm you are loading the original desktop wallet:
   ```bash
   getwalletinfo
   ```
   The output should display:
   ```bash
   "active_wallet" : "wallet_backup_2024-xx-xx-xx-xx-xx.dat"
   ```

---

### Step 6: Generate a New Address in the Backup Wallet

1. In Debug Console run the following command to generate a new receiving address in your original desktop wallet:
   ```
   getnewaddress
   ```

2. **Highlight and copy** the address from the console:
   - Use your mouse to **highlight** the address.
   - **Copy** the highlighted address using:
     - **Windows**: `Ctrl + C`
     - **macOS**: `Cmd + C`
   

3. In Debug Console run the following command to validate the address to confirm it belongs to your original desktop wallet:
   ```
   validateaddress <yournewaddress>
   ```
   Replace `<yournewaddress>` with the address you copied from **Step 5**. **Paste** the address using keyboard commands:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

4. Ensure the **`ismine`** field is set to **true**.
   ```bash
   "ismine" : true
   ```

### Step 7: Save the new address in migration.txt
1. Paste this address into your **migration.txt** document from Step 1 for safekeeping:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

2. **Save the file** using `Ctrl + S` on Windows or `Cmd + S` on macOS.

---

### Step 8: Return to Your imported Divi Wallet

1. After validating the address, load your imported Divi Mobile Wallet:
   ```
   loadwallet wallet.dat
   ```

---

### Step 9: Unlock Your Wallet

1. Unlock your imported Divi Mobile Wallet to send funds:
   ```
   walletpassphrase <yourpassword> 9999 false
   ```
   Replace `<yourpassword>` with your actual wallet password.

---

### Step 10: Send Funds to the New Address from your Original Desktop Wallet.

1. Send the funds to the address generated in **Step 5**:
   ```
   sendtoaddress <yournewaddress> <amount>
   ```
   Replace `<yournewaddress>` with the address from **Step 5**, and `<amount>` with the amount of Divi to transfer.

2. After sending, you will receive a **transaction hash (ID)**. Wait a few minutes for the transaction to confirm.

---

### Step 11: Load the Backup Wallet Again

1. Once the transaction is confirmed, load your original backup wallet again:
   ```bash
   loadwallet wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```

2. Verify you are in the correct wallet by running:
   ```bash
   getwalletinfo
   ```

---

### Step 12: Check Your Balance

1. To confirm the funds have been received, run:
   ```bash
   getbalance
   ```

---

### Step 13: Rename Wallet Files

1. **Close Divi Desktop** completely.

2. Open **File Explorer** and navigate to:
   ```
   AppData/Roaming/DIVI
   ```

3. **Rename the current `wallet.dat`** file to:
   ```
   wallet.mobile
   ```

4. **Rename your backup wallet** file:
   ```
   wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```
   to:
   ```
   wallet.dat
   ```

---

### Step 14: Reopen Divi Desktop

1. Reopen **Divi Desktop**. The application will now load your original wallet, and the funds from the mobile wallet will have been successfully migrated.

---

This tutorial guides you through safely moving your funds from the Divi Wallet Mobile to the original desktop wallet, making it the default once again. Ensure you save all important information in your **migration.txt** document to avoid mistakes during the process.
