## 🛠️ **Restore a Broken `YourWalletFileName.dat` Wallet Using a Backup (macOS)**

This guide walks you through restoring a broken `YourWalletFileName.dat` wallet file using a previous backup stored in the `monthlyBackups` folder.

---

### 🔁 Step 1: Close Divi Desktop

* Click the red ❌ **X in the top-left corner** of the Divi Desktop application window to shut it down completely.

---

### 🔍 Step 2: Open the DIVI directory

1. Open **Finder** (click the blue smiley face icon in your dock).

2. In the top menu bar, click **Go**, then choose **Go to Folder...** from the dropdown.

3. In the box that appears, type:

   ```
   ~/Library/Application Support/DIVI
   ```

4. Click **Go**.

This opens the folder where Divi Desktop stores your wallet files.

---

### 🗃️ Step 3: Rename the Broken Wallet

1. In the `DIVI` folder, find the file named:

   ```
   YourWalletFileName.dat
   ```

2. Right-click it and choose **Rename**.

3. Change the name to:

   ```
   YourWalletFileName.dat-broken
   ```

This keeps a copy of your broken wallet in case you need to go back to it.

---

### 🧾 Step 4: Use a Backup from `monthlyBackups`

1. In the same Finder window, double-click to open the folder named:

   ```
   monthlyBackups
   ```

2. Find the **second-to-last** backup file. It will be named something like:

   ```
   YourWalletFileName.dat.2025-03-03-09-14
   ```

3. Right-click that file and choose **Copy**.

4. Go back to the `DIVI` folder and **Paste** the file there.

5. Rename the pasted file to:

   ```
   YourWalletFileName.dat
   ```

---

### 🚀 Step 5: Start Divi Desktop

* Open **Divi Desktop** from your **Applications** folder or Dock.

* The application will start using the default wallet.dat to load the YourWalletFileName.dat, use console:
```
loadwallet YourWalletFileName.dat
```

