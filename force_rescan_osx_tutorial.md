# **Mac: Force Rescan on an Existing Seed-Restored Wallet**

This guide will walk you through performing a `-force_rescan=1` on an **existing wallet** in the Divi Desktop Application on macOS. This process is useful if your restored wallet isn't showing your coins or transactions after syncing.

Let’s get started!

---

### **Important Notes Before You Begin**
1. Ensure the Divi Desktop Application is **completely closed** before starting.
2. Do **NOT** rename or delete your `wallet.dat` file—this process works with your existing wallet.
3. This guide assumes your wallet is already restored, fully synced, and you are only rescanning the blockchain for your transactions.

---

## **Step A: Prepare for the Force Rescan**

1. Open Finder and press Command + Shift + G to open the "Go to Folder" dialog.
2. Type or copy and paste the following, then press **Enter**:
     ```
     ~/Library/Application Support/
     ```

4. Locate the **Divi Desktop** folder:
   - Navigate to the `Divi Desktop` directory inside `Application Support`.
   - Open the **Divi Desktop** folder (not `DIVI`).

5. Delete the `divitxs.db` file:
   - Inside the **Divi Desktop** folder, find and delete the `divitxs.db` file.  
   - If the file extension isn't visible, it may appear as `divitxs`.

6. Close the Finder window.

---

## **Step B: Perform the Force Rescan**

1. Open the Terminal application:
   - Use Spotlight Search by pressing `Command + Space`, type **Terminal**, and press **Enter**.

2. Navigate to the Divi daemon directory:
   - Copy and paste the following command into the Terminal and press **Enter**:
     ```bash
     cd ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked
     ```

3. Before running the daemon, make it executable by entering this command and pressing **Enter**: 
    ```bash
    chmod +x *
    ```

4. Run the force rescan command:
   - Execute the following command in the Terminal to initiate the rescan and press **Enter**:
     ```bash
     ./divid -force_rescan=1
     ```

5. You should see output similar to **"Divi Server Starting"**.

6. Wait for the process to run:
   - Allow the force rescan to run for approximately **5 minutes**. Do not close the Terminal during this process.
   - Proceed to **Step C** after waiting.

---

## **Step C: Reopen Divi Desktop and Verify**

1. Launch the Divi Desktop Application from your **Applications** folder or Dock.
2. Allow it to fully sync with the blockchain.  
3. Verify that your coins and transaction history appear under the **Overview** and **History** tabs.

---

## **Step D: Finalize and Secure Your Wallet**

1. Set a **strong and secure password** for your wallet if you haven’t already:
   - Open **Settings** in the Divi Desktop Application and configure a password for added security.
2. Close the Divi Desktop Application to complete the process.
3. Exit the Terminal by typing the following command and pressing **Enter**:
    ```bash
    exit
    ```
   Alternatively, you can simply close the Terminal window.

---

### **Important Notes**
- This process rescans the blockchain for your wallet's transactions without creating a new wallet file.  
- Your existing `wallet.dat` file remains intact, preserving all your previous data.

---

## **Need Help?**

If you encounter issues or need assistance, join the Divi community for real-time support:

- **Discord**: [https://discord.diviproject.org](https://discord.gg/diviproject)  
- **Telegram**: [https://telegram.diviproject.org](https://t.me/diviproject)  

Stay secure, and happy staking! 😊



# **NEVER STORE YOUR SEED WORDS (Seed Phrases, Recovery Phrases) IN A PHOTOGRAPH OR TEXT DOCUMENT (e.g., Photos, Notes, Pages, Google Docs, etc.)—EVER!**

