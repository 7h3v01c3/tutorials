# **Ubuntu: Force Rescan on an Existing Seed-Restored Wallet**

This guide will walk you through performing a `-force_rescan=1` on an **existing wallet** in the Divi Desktop Application on Ubuntu Linux. This process helps if your restored wallet isn't showing your coins or transactions after syncing.

Let's get started!

---

### **Important Notes Before You Begin**

1. Ensure the Divi Desktop Application is **completely closed** before starting.
2. Do **NOT** rename or delete your `wallet.dat` file. This process works with your existing wallet.
3. This guide assumes your wallet is already restored, and you are only rescanning the blockchain for your transactions.
4. **Do NOT enter your seed words.** They are not needed for this procedure.

---

## **Step A: Prepare for the Force Rescan**

1. **Close the Divi Desktop Application completely.**

2. **Open the Files application:**
   - Click the Files icon on your Ubuntu desktop.
   - Alternatively, open **Show Applications** and search for **Files**.

3. **Show hidden files and folders:**
   - Press `Ctrl + H` to display hidden directories.
   - These directories begin with a period (`.`).

4. **Navigate to the Divi Desktop configuration directory:**
   - Open your Home directory.
   - Open the `.config` folder.
   - Locate and open the `divi-desktop` folder.

   The complete path is:

   ```text
   ~/.config/divi-desktop/
   ```

5. **Delete the `divitxs.db` file:**
   - Inside the `divi-desktop` folder, locate `divitxs.db`.
   - Delete **only** the `divitxs.db` file.
   - This file stores transaction data used by Divi Desktop and will be rebuilt during the rescan.
   - Do not delete other files or folders.

6. Close the Files application.

---

### Keep These Tutorials Going

These tutorials are freely shared to help others learn, solve problems, and pass that knowledge on.

**[If this helped you, consider supporting the work and helping keep these tutorials going →](https://thevoice.dev/#donations)**

---

## **Step B: Perform the Force Rescan**

1. **Open the Terminal application:**
   - Press `Ctrl + Alt + T`.
   - Alternatively, search for **Terminal** in Applications.

2. **Navigate to the Divi daemon directory:**

   Copy and paste the following command into Terminal, then press **Enter**:

   ```bash
   cd ~/.config/divi-desktop/divid/unpacked/divi_ubuntu
   ```

   This is the Ubuntu daemon directory documented in the Divi Desktop wallet-recovery tutorial.

3. **Before running the daemon, make it executable:**

   Enter the following command:

   ```bash
   chmod +x ./divid
   ```

   Press **Enter**.

4. **Run the force rescan command:**

   Copy and paste the following command into Terminal, then press **Enter**:

   ```bash
   ./divid -force_rescan=1
   ```

   You should see output similar to:

   ```text
   DIVI server starting
   ```

   **Important:** You are not recovering a new wallet. Do not add the `-mnemonic` argument or enter your seed phrase.

5. **Wait approximately 5 minutes.**
   - Leave the Terminal window open.
   - Do not close it during this process.
   - Proceed to **Step C**.

---

## **Step C: Reopen Divi Desktop and Verify**

1. Launch the Divi Desktop Application.
2. Allow it to fully sync with the blockchain.
3. Verify that your coins and transaction history appear under **Overview** and **History**.
4. If your wallet is still syncing or scanning, allow the process to complete before assuming transactions are missing.

---

## **Step D: Finalize and Secure Your Wallet**

1. Set a **strong and secure password** for your Divi Desktop Application if you haven't already:
   - Open the application's **Security Settings**.
   - Configure your wallet password.

2. Fully close the Divi Desktop Application to complete the process.

3. Exit the Terminal:
   - If the daemon process is still attached to Terminal, stop it gracefully and wait for it to exit before closing the window.
   - Then type:

   ```bash
   exit
   ```

   Alternatively, close the Terminal window after the daemon has stopped.

---

### **Important Notes**

- This process rescans the blockchain for your wallet's transactions without creating a new wallet file.
- Your existing `wallet.dat` file remains intact, preserving your wallet data.
- Ubuntu uses different application directories than Windows and macOS.
- Your existing wallet data directory, `~/.divi/`, must not be deleted or renamed during this procedure.

---

## **Need Help?**

If you encounter issues or need assistance, join the Divi community for real-time support:

- **Discord**: [https://discord.gg/diviproject](https://discord.gg/diviproject)
- **Telegram**: [https://t.me/diviproject](https://t.me/diviproject)

Stay secure, and happy staking! 😊

---

# **NEVER STORE YOUR SEED WORDS (Seed Phrases, Recovery Phrases) IN A PHOTOGRAPH OR TEXT DOCUMENT (e.g., Photos, Notes, Google Docs, etc.)—EVER!**
