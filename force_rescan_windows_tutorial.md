# **Windows: Force Rescan on an Existing Seed-Restored Wallet**

This guide will walk you through performing a `-force_rescan=1` on an **existing wallet** in the Divi Desktop Application. This process helps if your restored wallet isn't showing your coins or transactions after syncing.

Let’s get started!

---

### **Important Notes Before You Begin**
1. Ensure the Divi Desktop Application is **completely closed** before starting.
2. Do **NOT** rename or delete your `wallet.dat` file—this process works with your existing wallet.
3. This guide assumes your wallet is already restored, and you are only rescanning the blockchain for your transactions.

---

## **Step A: Prepare for the Force Rescan**


1. **Close the Divi Desktop Application completely.**
2. Open a Run dialog box with `Windows Key + R`.
3. Type `%appdata%` and hit **Enter**.

Example:
Open the AppData Roaming in File Explorer as shown below:

![AppData Screenshot](https://github.com/7h3v01c3/tutorials/blob/main/images/appdata.png)

4. Navigate to the **Divi Desktop** folder.
    Delete only the divitxs.db file in the Divi Desktop folder.
    - This file stores temporary transaction data and will be rebuilt during the rescan.
    - Note: The .db extension may not be visible, and you might only see divitxs as the file name.

Example:
Delete the divitxs.db file:

![AppData Screenshot](https://github.com/7h3v01c3/tutorials/blob/main/images/divitxs-db.png)


---

## **Step B: Perform the Force Rescan**

1. Open a Run dialog box with `Windows Key + R`.
2. Type `cmd` and hit **Enter** or click "OK" to open the Command Prompt.

Example:
Open the Command Prompt as shown below:

![CMD Screenshot](https://github.com/7h3v01c3/tutorials/blob/main/images/cmd.png)

3. Navigate to the Divi daemon directory:

Example:
Navigate to the correct directory in your AppData folder:

![AppData Full Path](https://github.com/7h3v01c3/tutorials/blob/main/images/appdata-full-path-divi-win-64.png)

   ```
   cd %appdata%/"Divi Desktop"/divid/unpacked/divi_win_64
   ```

4. Run the force rescan command:

Example
Run the following command to initiate the rescan:

![Divi Force Rescan](https://github.com/7h3v01c3/tutorials/blob/main/images/divid-force-rescan.png)

   ```
   divid.exe -force_rescan=1
   ```

5. Wait about 5 Minutes. 
  - Leave this CMD window running and open until Step D.

---

## **Step C: Reopen Divi Desktop and Verify**

1. Launch the Divi Desktop Application.
2. Allow it to fully sync with the blockchain.  
3. Verify that your coins and transaction history appear in overview and history.


---

## **Step D: Finalize and Secure Your Wallet**

1. Double-check that you've set a **strong and secure password** for your Divi Desktop Application. If you haven’t done so yet, navigate to the **Security Settings** in the application and set a password now. This ensures your wallet is protected.  
2. Fully close the Divi Desktop Application to complete the process.  
3. Exit the Command Prompt (CMD) window by clicking the "X" or typing `exit` and pressing Enter.  

---

> **Important:** This process rescans the blockchain for your wallet's transactions without creating a new wallet file. By keeping your `wallet.dat` intact, all your previous data is preserved during the rescan.

If you have further questions or issues, join the community for real-time help:

- **Discord**: [https://discord.gg/diviproject](https://discord.gg/diviproject)
- **Telegram**: [https://t.me/diviproject](https://t.me/diviproject)

Stay secure, and happy staking! 😊

---
# **NEVER STORE YOUR SEED WORDS (Seed Phrases, Recovery Phrases) IN A TEXT DOCUMENT (e.g., Notepad, WordPad, Word, Google Docs, etc.)—EVER!**



