
# **DO NOT EVER SAVE YOUR SEED WORD IN A TEXT DOCUMENT - EVER!**

## Windows Recovery of Divi Wallet in Divi Desktop Application

---

**Make sure the Divi Desktop Application is closed before starting.**

Hi everyone! In today’s tutorial, I’ll walk you through the process of recovering your Divi Wallet using the Divi Desktop Application. We’ll go step-by-step through the recovery process using your mnemonic (seed phrase) and the terminal.

Let’s get started!

---

### Syntax for Recovery:
```
divid.exe -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1
```

### Path in Terminal:
```
cd %appdata%/"Divi Desktop"/divid/unpacked/divi_win_64
```

### Prep Work:
1. Divi Desktop should be installed and synced.

---

## Step A: Prepare for Wallet Recovery

1. Open a run dialog box with `Windows Key + R`.  
2. Enter `%appdata%` and hit Enter.
3. OPEN DIVI (Not Divi Desktop)
3. Rename `wallet.dat` to `wallet_backup.dat`.
*dont be suprised when windows asks permission*
After renaming move to 4.
4. Close the File Explorer window.

---

## Step B: Recover Your Divi Wallet

1. Open a run dialog box with `Windows Key + R`.  
2. Enter `cmd` and click OK.  
3. Navigate to the daemon using the path provided:
    ```
    cd %appdata%/"Divi Desktop"/divid/unpacked/divi_win_64
    ```
4. Enter the recovery command with your seed words:
    ```
    divid.exe -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1
    ```
    Replace `word1` through `word12` with your seed word phrase, all lowercase, with a single space between each word.

5. Wait a few moments, then open the Divi Desktop Application.

---

## Final Steps:

1. Let the app sync completely and wait for your coins to appear in the balance.
2. Close the Divi Desktop Application.
3. Close the Windows Terminal.

> **Note:** Step 1 must happen before closing the application (Step 2)—do not change the order!

You're all set at recovering your Divi wallet in the Divi Desktop Application.

