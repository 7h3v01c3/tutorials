# **NEVER STORE YOUR SEED WORDS (Seed Phrases, Recovery Phrases) IN A TEXT DOCUMENT (e.g., Notepad, WordPad, Word, Google Docs, etc.)—EVER!**

---

## **Windows: Force Rescan on an Existing Seed-Restored Wallet**

This guide will walk you through performing a `-force_rescan=1` on an **existing wallet** in the Divi Desktop Application. This process helps if your restored wallet isn't showing your coins or transactions after syncing.

Let’s get started!

---

### **Important Notes Before You Begin**
1. Ensure the Divi Desktop Application is **completely closed** before starting.
2. Do **NOT** rename or delete your `wallet.dat` file—this process works directly on your existing wallet.
3. This guide assumes your wallet is already restored, and you are only rescanning the blockchain for your transactions.

---

## **Step A: Prepare for the Force Rescan**

1. **Close the Divi Desktop Application completely.**
2. Open a Run dialog box with `Windows Key + R`.
3. Type `%appdata%` and hit **Enter**.
4. Navigate to the **Divi Desktop** folder.
5. Delete **only** the `divitxs.db` file in the **Divi Desktop** folder.
    - *This file stores temporary transaction data and will be rebuilt during the rescan.*

---

## **Step B: Perform the Force Rescan**

1. Open a Run dialog box with `Windows Key + R`.
2. Type `cmd` and hit **Enter** to open the Command Prompt.
3. Navigate to the Divi daemon directory:
   ```
   cd %appdata%/"Divi Desktop"/divid/unpacked/divi_win_64
   ```
4. Run the force rescan command:
   ```
   divid.exe -force_rescan=1
   ```
5. Let the process complete. This may take some time depending on your wallet and blockchain sync status.
  - Leave this CMD window open while scanning

---

## **Step C: Reopen Divi Desktop and Verify**

1. Launch the Divi Desktop Application.
2. Allow it to fully sync with the blockchain.  
3. Verify that your coins and transaction history appear in overview and history.


---

### **Final Steps**
1. Set a strong password for your Divi Desktop Application if you haven’t already done so.
2. Close the Divi Desktop Application, exit completely.
3. Close "X" the cmd window now!

---

> **Important:** This process rescans the blockchain for your wallet's transactions without creating a new wallet file. By keeping your `wallet.dat` intact, all your previous data is preserved during the rescan.

If you have further questions or issues, join the community for real-time help:

- **Discord**: [https://discord.gg/diviproject](https://discord.gg/diviproject)
- **Telegram**: [https://t.me/diviproject](https://t.me/diviproject)

Stay secure, and happy staking! 😊
