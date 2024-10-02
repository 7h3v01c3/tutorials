# **DO NOT EVER SAVE YOUR SEED WORD IN A TEXT DOCUMENT - EVER!**

## Windows Recovery of Divi Wallet in Divi Desktop Application

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

## Part 1: Prepare for Wallet Recovery

**A.** Open a run dialog box with `Windows Key + R`.  
**B.** Enter `%appdata%` and hit Enter.  
**C.** Rename `wallet.dat` to `wallet_backup.dat`.  
**D.** Close the File Explorer window.

---

## Part 2: Recover Your Divi Wallet

**A.** Open a run dialog box with `Windows Key + R`.  
**B.** Enter `cmd` and click OK.  
**C.** Navigate to the daemon using the path provided:
```
cd %appdata%/"Divi Desktop"/divid/unpacked/divi_win_64
```
**D.** Enter the recovery command with your seed words:
```
divid.exe -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1
```
Replace words1-12 with your seed word phrase, all lowercase with a single space between each word.

**E.** Wait a few moments, then open the Divi Desktop Application.

---

## Final Steps:

A. Let the app sync completely and wait for your coins to appear in the balance.  
B. Close the Divi Desktop Application.  
C. Close the Windows Terminal.

> **Note:** Step 4 must happen before step 5—do not change the order!

You're all set at recovering your Divi wallet in the Divi Desktop Application.
