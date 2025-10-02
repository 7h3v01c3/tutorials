# ⚠️ DO NOT EVER SAVE YOUR SEED WORDS (seed phrases, recovery phrases) IN A TEXT DOCUMENT — EVER!

# # 🐧 Ubuntu Recovery of Divi Wallet in Divi Desktop Application

<sub>📝 Tutorials are voluntary & kept free by donations — see bottom for support.</sub>

---

**Make sure the Divi Desktop Application is closed before starting.**

**Note:** Don't forget to set a password for Divi Desktop after you have migrated into Divi Desktop.

Hi everyone! In today's tutorial, I'll walk you through recovering your Divi Wallet using the Divi Desktop Application on **Ubuntu**. We'll go step-by-step through the recovery process using your mnemonic (seed phrase) and the terminal.

Let's get started!

---

## ✅ Syntax for Recovery:

```bash
./divid -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1 &
```

**Note:** If you encounter the error:  
`Error: There is no RPC client functionality in divid anymore. Use the divi-cli utility instead.`  
This error usually indicates a syntax error. Review your command for missing or incorrect quotes (`"`), hyphens (`-`), or spelling mistakes.

---

## 📂 Path in Terminal:

```bash
cd ~/.config/divi-desktop/divid/unpacked/divi_ubuntu
```

---

## 🛠️ Step A: Prepare for Wallet Recovery

A. Close Divi Desktop Application  
- If running, close it completely

1. **Open the Files App**:
   - Click the Files icon on the left sidebar or  
   - Open the bottom-left corner "Show Applications" icon and search for **Files**

2. **Show Hidden Files**:
   - Press `Ctrl + H` to display hidden files/folders (those starting with a `.`)

   Take note of two directories:  
   A. `.divi`  
   B. `.config`  
   These are the two directories we will be working from. Now that you know which directories we will be working in, proceed to step 3.

3. **Locate Wallet Backup**:
   - Open `.divi` folder:
     ```
     .divi
     ```
   - Find `wallet.dat`  
   - Rename it to:
     ```
     wallet_backup.dat
     ```
   - Right-click → Rename, or press `F2` to rename. Confirm rename when done.

4. **Delete `divitxs.db` File**:
   - Now move from the `.divi` folder and open the `.config` folder:
     ```
     Inside .config, locate and open the divi-desktop folder
     ```
   - Delete:
     ```
     divitxs.db
     ```
   - Close the Files App

---

## 💻 Step B: Recover Your Divi Wallet

1. **Open Terminal**:
   - Use shortcut `Ctrl + Alt + T` or search and open "Terminal" from Applications

2. **Navigate to the Divi Daemon Directory**:
   ```bash
   cd ~/.config/divi-desktop/divid/unpacked/divi_ubuntu
   ```
   TIP: To make your terminal window wider, mouse to the right edge until you see the arrows, and click-drag to the right.

3. **Give yourself permission to run Divi Core**:  
   In the terminal, enter:
   ```bash
   chmod +x *
   ```

4. **Run the Recovery Command**:  
   In the terminal enter, replacing `"word1 word2 ..."` with your actual seed words:
   ```bash
   ./divid -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1 &
   ```
   You should see DIVI server starting.

   **Make sure:**
   - All words are lowercase
   - Use only one space between each word
   - Quotes must be `"` — **not** `'`

   If you see:
   ```
   Error: There is no RPC client functionality in divid anymore. Use the divi-cli utility instead.
   ```
   → There's probably a typo or formatting issue. Double-check.

   If you see:
   ```
   SetMnemonic: invalid mnemonic: please check your words
   ```
   → Simple: you misspelled the words. Try again, spelling your words correctly.
   ! Leave terminal running and proceed to Step 5.

5. Wait a few moments, then open the Divi Desktop Application.

   - Proceed to Final Steps

---

## 🎯 Final Steps

1. Let the Divi Desktop Application sync completely and wait for your coins to appear in the **Total Balance** (top left).
2. After Fully Synced, Fully Confirmed Balance
   A. Close Divi Desktop
   B. Close Terminal
3. Wait 30 Seconds
4. Restart Divi Desktop
5. Allow to sync fully (balance showing, fully synced in bottom left corner)
**DON'T FORGET TO SET A PASSWORD**
6. Set a password

> **Note:** For the Final Steps, Step 2 is process order, dont change or mix.

💡 **If this tutorial helped you, consider supporting the author.** All guides are created through voluntary effort — your donation keeps them coming. 👉 [Support here](https://www.thevoice.dev/#donations)

---

> ✅ You're now fully recovered on Ubuntu like a pro. No GUI sorcery — just clean CLI power.
