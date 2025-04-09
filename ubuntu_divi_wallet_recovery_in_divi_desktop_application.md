# ⚠️ DO NOT EVER SAVE YOUR SEED WORDS (seed phrases, recovery phrases) IN A TEXT DOCUMENT — EVER!

# # 🐧 Ubuntu Recovery of Divi Wallet in Divi Desktop Application

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

---

## 🎯 Final Steps

1. Leave the terminal open and running (minimize it out of the way)  
2. Then Launch the **Divi Desktop Application**  
3. Let it **sync completely**  
4. Check for your balance in the **Total Balance** section (top left)  
5. Set a **strong password**  
6. **Close Divi Desktop first**, then close the **Terminal**

---

> ✅ You're now fully recovered on Ubuntu like a pro. No GUI sorcery — just clean CLI power.
