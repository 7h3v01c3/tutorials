### **Windows Steps to Migrate funds from an old seed(wallet) to a new seed (wallet) in and existing Divi Desktop**

#### **1. Access the Debug Console**
1. Open the **Divi Desktop Application**.
2. Enable **Advanced Mode**:
   - Navigate to **Settings** (Gear Icon in the navigation bar on the left).
   - On the **General Tab**, ensure that the box for **Advanced Mode** is checked.
3. Open the **Debug Console**:
   - Locate the console icon in the top-right corner of the application.
4. Unlock your wallet when prompted:
   - Select a timeout option from the dropdown (e.g., 20 minutes).

---

#### **2. Load Your New Wallet**
1. In the Debug Console, type the following command:
   ```
   loadwallet newwallet.dat
   ```
   - **Note**: Ensure the wallet file name is spelled perfectly. If you mistype it, a new wallet will be created with the incorrect name, causing confusion.
2. Wait a few seconds for the wallet to load.
3. Check the wallet details:
   ```
   getwalletinfo
   ```
   - Verify the output includes:
     ```
     "active_wallet": "newwallet.dat",
     ```

---

#### **3. Back Up Your New Wallet Seed Words**
1. Run the following command in the Debug Console:
   ```
   dumphdinfo
   ```
2. Carefully write down and securely store the new seed words. This step is essential for future recovery.

---

#### **4. Generate and Validate a Receiving Address**
1. Generate a new receiving address:
   ```
   getnewaddress
   ```
2. Validate the generated address:
   ```
   validateaddress <your_new_address>
   ```
   - Look for the `"ismine"` field in the output. If `"ismine": true`, it confirms that the address is controlled by your new wallet.
3. Example output:
   ```json
   {
     "isvalid": true,
     "address": "DBi2owHex4aJUVGbgJbCPZgSRFvNWfi4xa",
     "ismine": true,
     "hdkeypath": "m/44'/301'/0'/0/1"
   }
   ```
4. Copy and securely store the validated address. You’ll use this address in Step 6.

---

#### **5. Switch Back to Your Old Wallet**
1. Load your old wallet:
   ```
   loadwallet wallet.dat
   ```
   - **Note**: Double-check the wallet name for accuracy.
2. Wait 30 seconds for the wallet to load.
3. Unlock the wallet if prompted.

---

#### **6. Test a Small Transaction**
1. Send a small test amount (e.g., 1 DIVI) from your old wallet to the address you generated in Step 4.
2. Wait for the transaction to confirm.
3. Switch to your new wallet:
   ```
   loadwallet newwallet.dat
   ```
4. Verify the test transaction:
   ```
   getinfo
   ```
   Example output:
   ```json
   {
     "balance": 1.00000000,
     "staking status": "Staking Active",
     "errors": ""
   }
   ```
   - **Key Field to Check**:
     - `"balance": 1.00000000` – Verify that the test transaction amount (1 DIVI) is reflected in your new wallet balance.

---

#### **7. Transfer Your Full Balance**
1. Switch back to your old wallet:
   ```
   loadwallet wallet.dat
   ```
2. Unlock the wallet if needed.
3. Transfer your entire balance to the new wallet address.
4. Wait for the transaction to confirm.

---

### **8. Final Steps for Migration**

#### **Close Divi Desktop**
1. Ensure the Divi Desktop Application is fully closed.
   - Click the **X** in the top corner of the app.
   - Confirm that the application has exited completely.

---

#### **Navigate to the Wallet Directory**
1. Open the **Run Dialog Box**:
   - Press `Windows Key + R` on your keyboard.
   - Type `%appdata%` and press **Enter**. This will open the AppData/Roaming folder.
2. Locate the **DIVI Folder**:
   - You will see two folders: `DIVI` and `Divi Desktop`. Start with the `DIVI` folder.

---

#### **Backup and Replace Wallet Files**
1. Inside the **DIVI Folder**:
   - Locate `wallet.dat` and rename it to `wallet_backup.dat`.  
     *(Windows may prompt you to confirm this change.)*
   - Rename `newwallet.dat` to `wallet.dat`.
2. Ensure the changes are saved.

---

#### **Delete Cache Files in Divi Desktop**
1. Navigate **up one directory** and open the `Divi Desktop` folder.
2. Locate and delete the following file:
   ```
   divitxs.db
   ```
   - This clears the transaction cache to ensure a clean sync after migration.
3. Close File Explorer.

---

#### **Restart Divi Desktop**
1. Open the Divi Desktop Application.
2. Confirm that the migration was successful and that your balance is intact.

---

#### **9. Encrypt Your Wallet**
1. Once Divi Desktop loads, click the **black triangle warning symbol**.
2. Encrypt your wallet for added security. Ensure your encryption passphrase is stored securely.

---
