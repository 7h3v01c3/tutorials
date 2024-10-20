### Migrating Funds from Divi Mobile Wallet to Original Desktop Wallet

---

### Overview

This guide will help you migrate funds from the **Divi Wallet Mobile** (now unsupported) to the **Divi Desktop** wallet. You will move funds from the newly imported mobile wallet to your original desktop wallet. The steps also include renaming the wallet files to set the original wallet as the default.

---

### Step 1: Prepare and Save Important Information

1. **Open a Text Editor**:
   - **Windows**: Press `Alt + Space`, type `notepad`, and hit **Enter**.
   - **macOS**: Press `CMD + Space`, type `TextEdit`, and hit **Enter**.
   
2. **Create and Save the Document**:
   - Name the file something meaningful, like `migration.txt`, and save it on your **Desktop** for easy access.
   
Here is the revised **Step 3** with your changes incorporated:

---

### Step 3: Locate Your Original Wallet Backup

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

---

4. **Save the file** using `Ctrl + S` on Windows or `Cmd + S` on macOS.

---

### Step 2: Log In to Divi Desktop and Enable Debug Console

1. **Open Divi Desktop** and log in.
2. Open **Debug Console** 
   - If Debug Console isnt visible
     - **Enable Debug Console**:
        - Go to **Settings**.
        - On the **General** tab, check the box for **Advanced Mode**.
     - Once **Advanced Mode** is enabled, the **Debug Console** will be visible at the top. Click it to open the console.

---

### Step 3: Verify Current Wallet

1. **Unlock your wallet** if necessary.
   
2. Run the following command to check the current wallet you're using:
   ```bash
   getwalletinfo
   ```
   
3. The output will show that you're in the **default wallet**, which is typically the 12-word seed phrase wallet:
   ```
   wallet.dat
   ```

---

### Step 4: Load the Original Backup Wallet

1. To access your original backup wallet, run the following command, **replacing the date** with the one you copied in **Step 1**:
   ```bash
   loadwallet wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```
   **Important**: Do **not** manually type the file name. **Copy** the name from your **migration.txt** document and **paste** it using keyboard commands:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

   **Spelling errors will create a new wallet, causing issues. Double-check your pasted entry** to avoid mistakes.

2. Wait about 60 seconds for the wallet to load.

3. Confirm you are in the correct wallet by running:
   ```bash
   getwalletinfo
   ```
   The output should display:
   ```
   wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```

---

### Step 5: Generate a New Address in the Backup Wallet

1. Run the following command to generate a new receiving address in your original wallet:
   ```bash
   getnewaddress
   ```

2. **Highlight and copy** the address from the console:
   - Use your mouse to **highlight** the address.
   - **Copy** the highlighted address using:
     - **Windows**: `Ctrl + C`
     - **macOS**: `Cmd + C`
   

3. Run the following command to validate the address to confirm it belongs to your original wallet:
   ```bash
   validateaddress <yournewaddress>
   ```
   Replace `<yournewaddress>` with the address you copied from **Step 5**. **Paste** the address using keyboard commands:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

4. Ensure the **`ismine`** field is set to **true**.

### Step 6: Save the new address in migration.txt
1. Paste this address into your **migration.txt** document from Step 1 for safekeeping:
   - **Windows**: `Ctrl + V`
   - **macOS**: `Cmd + V`

2. Save the document again.

---

### Step 7: Return to Your Seed Phrase Wallet

1. After validating the address, load your 12-word seed phrase wallet again by running:
   ```bash
   loadwallet wallet.dat
   ```

---

### Step 8: Unlock Your Wallet

1. Unlock your seed phrase wallet to send funds:
   ```bash
   walletpassphrase <yourpassword> 9999 false
   ```
   Replace `<yourpassword>` with your actual wallet password.

---

### Step 9: Send Funds to the New Address

1. Send the funds to the address generated in **Step 5**:
   ```bash
   sendtoaddress <yournewaddress> <amount>
   ```
   Replace `<yournewaddress>` with the address from **Step 5**, and `<amount>` with the amount of Divi to transfer.

2. After sending, you will receive a **transaction hash (ID)**. Wait a few minutes for the transaction to confirm.

---

### Step 10: Load the Backup Wallet Again

1. Once the transaction is confirmed, load your original backup wallet again:
   ```bash
   loadwallet wallet_backup_2024-xx-xx-xx-xx-xx.dat
   ```

2. Verify you are in the correct wallet by running:
   ```bash
   getwalletinfo
   ```

---

### Step 11: Check Your Balance

1. To confirm the funds have been received, run:
   ```bash
   getbalance
   ```

---

### Step 12: Rename Wallet Files

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

### Step 13: Reopen Divi Desktop

1. Reopen **Divi Desktop**. The application will now load your original wallet, and the funds from the mobile wallet will have been successfully migrated.

---

This tutorial guides you through safely moving your funds from the Divi Wallet Mobile to the original desktop wallet, making it the default once again. Ensure you save all important information in your **migration.txt** document to avoid mistakes during the process.
