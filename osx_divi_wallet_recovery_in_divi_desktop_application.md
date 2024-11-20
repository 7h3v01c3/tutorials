# **DO NOT EVER SAVE YOUR SEED WORDS (seed phrases, recovery phrases) IN A TEXT DOCUMENT - EVER!**

## Mac Recovery of Divi Wallet in Divi Desktop Application

---

**Make sure the Divi Desktop Application is closed before starting.**

**Note: Don't forget to set a password for Divi Desktop after you have migrated into Divi Desktop.**

Hi everyone! In today’s tutorial, I’ll walk you through the process of recovering your Divi Wallet using the Divi Desktop Application on macOS. We’ll go step-by-step through the recovery process using your mnemonic (seed phrase) and the terminal.

Let’s get started!

---

### Syntax for Recovery:
```
./divid -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1 &
```
**Note:** If you encounter the error:  
*Error: There is no RPC client functionality in divid anymore. Use the divi-cli utility instead.*,  
this usually indicates a syntax error. Review your command for missing or incorrect quotes (`"`), hyphens (`-`), or spelling mistakes.


### Path in Terminal:
```
cd ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx
```

### Prep Work:
1. Divi Desktop should be installed, fully synced and shutdown.

---

## Step A: Prepare for Wallet Recovery

1. Open Finder and press `Command + Shift + G` to open the "Go to Folder" dialog.
2. Enter `~/Library/Application Support` and click "Go."
3. Navigate to the **DIVI** folder (not Divi Desktop).
4. Rename `wallet.dat` to `wallet_backup.dat`.
   *Note: macOS may ask for permission.* If you make a mistake with the name or extension, simply start over, then proceed to step 5.
5. Now, move back up one level in finder and enter into the **Divi Desktop** folder.
6. Delete **only** the `divitxs.db` file in the Divi Desktop folder.
7. Close the Finder window.

---

## Step B: Recover Your Divi Wallet

1. Open the **Terminal** application (you can find it in Applications > Utilities or search using Spotlight).
2. Navigate to the Divi daemon folder using the path below:
    ```
    cd ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx
    ```
3. Before running the daemon, make it executable by entering:
    ```
    chmod +x *
    ```
4. Now, run the following recovery command, replacing `word1` through `word12` with your actual seed words:
    ```
    ./divid -mnemonic="word1 word2 word3 word4 word5 word6 word7 word8 word9 word10 word11 word12" -force_rescan=1 &
    ```
    Make sure your seed words are all lowercase, with a single space between each word.

**Note:** If you encounter the error:  
*Error: There is no RPC client functionality in divid anymore. Use the divi-cli utility instead.*,  
this usually indicates a syntax error. Review your command for missing or incorrect quotes (`"`), hyphens (`-`), or spelling mistakes.


5. Wait a few moments, then open the Divi Desktop Application.

---

## Final Steps:

**DON'T FORGET TO SET A PASSWORD**

1. Let the Divi Desktop Application sync completely and wait for your coins to appear in the **Total Balance** (top left).
2. Set a Password for Divi Desktop (follow the process).
3. Close the Divi Desktop Application.
4. Close the Terminal.

> **Note:** For the Final Steps, step 3 must happen before closing the terminal (step 4)—do not change the order!

You're all set at recovering your Divi wallet in the Divi Desktop Application on macOS.
