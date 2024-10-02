# **DO NOT EVER SAVE YOUR SEED WORDS (seed phrases, recovery phrases) IN A TEXT DOCUMENT - EVER!**

## Windows Recovery of Divi Wallet in Divi Desktop Application

---

**Make sure the Divi Desktop Application is closed before starting.**

**Dont forget to set a password for Divi Desktop once finished**

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
3. Navigate to the **DIVI** folder (not Divi Desktop).  
4. Rename `wallet.dat` to `wallet_backup.dat`.  
   *Don’t be surprised when Windows asks for permission.* After renaming, move to step 5.  
5. Now, move up one level and enter into the **Divi Desktop** folder.
6. Delete **only** the `divitxs.db` file, in Divi Desktop folder.  
7. Close the File Explorer window.

---

## Step B: Recover Your Divi Wallet

1. Open a run dialog box with `Windows Key + R`.  
2. Enter `cmd` and click OK.  
3. Navigate to the daemon using the path provided:
   Either type this into your command window or paste it and hit enter.
    ```
    cd %appdata%/"Divi Desktop"/divid/unpacked/divi_win_64
    ```
5. Enter the recovery command with your seed words:
   At the command line now enter the following comman, below is the syntax.
    ```
    divid.exe -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1
    ```
    Replace `word1` through `word12` with your seed word phrase, all lowercase, with a single space between each word.

6. Wait a few moments, then open the Divi Desktop Application.

---

## Final Steps:

**DONT FORGET TO SET A PASSWORD**

1. Let the Divi Desktop Application sync completely and wait for your coins to appear in the **Total Balance** (top left).
2. Set a Password for Divi Desktop (follow the process)
3. Close the Divi Desktop Application.  
4. Close the Windows Terminal.

> **Note:** For the Final Steps, step 3 must happen before closing the terminal (step 4)—do not change the order!

You're all set at recovering your Divi wallet in the Divi Desktop Application.
