# **Divi Desktop Application Wallet Migration (Windows to Linux)**

## **Prerequisites**
For this process, you will need:
- **1 USB flash drive or external storage device**
- **1 Windows computer (Source) and 1 Linux computer (Recipient)**

---

## **Step 1: Prepare the Recipient Linux System**
1. **Download and Install the Divi Wallet**
   - Go to [Divi Project Downloads](https://diviproject.org/downloads).
   - Download and install the latest version of the wallet.
   - Open the Divi Desktop and **let it fully sync** before proceeding.
   - *You do not need to backup or encrypt at this step.*

---

## **Step 2: Backup the Source Windows Computer**
1. **Close Divi Desktop Completely**
   - Click the **X** in the top right corner to close the application.
   - *Ensure Divi Desktop is fully closed before continuing.*

2. **Open the AppData Folder**
   - Press **Windows Key + R** to open the Run dialog.
   - Type **`%appdata%`** and press **Enter**.
   - Locate and open the **DIVI** folder (**Do not mistakenly open `Divi Desktop` folder**).

3. **Copy the Following Files and Folders:**
   - `backups` (folder)
   - `monthlyBackups` (folder)
   - `wallet.dat`

4. **Paste the copied items onto your USB flash drive or external storage.**
   - This USB now contains a **backup** of your wallet.

---

## **Step 3: Restore on the Recipient Linux System**
1. **Ensure the Wallet is Fully Synced**
   - Let the wallet sync **completely** before proceeding. **(No need to set up anything, just allow it to sync.)**

2. **Close Divi Desktop Completely**
   - Click the **X** in the top left corner to close the application.
   - *Ensure Divi Desktop is fully closed before continuing.*

3. **Open the Hidden `.divi` Folder**
   - Open your **File Manager**.
   - Press **CTRL + H** to reveal hidden folders.
   - Open:
     ```
     .divi
     ```

4. **Delete the Following Files and Folders:**
   - `backups` (folder)
   - `monthlyBackups` (folder)
   - `wallet.dat`

5. **Copy and Paste from the USB Drive**
   - Transfer the backed-up files from your USB flash drive into the **.divi** folder on the recipient computer.
     - `backups` (folder)
     - `monthlyBackups` (folder)
     - `wallet.dat`
   - Close **File Manager**.

6. **Start Divi Desktop Application**
   - Open Divi Desktop Application.
   - Your wallet should now be restored but confirm!

7. **Confirm**
   - View **Balances** and **History**.
   - Your old wallet should now be restored on the Linux machine.

8. **Troubleshooting**
   - If you do not see your balance or transaction history:
     - Check your seed words:
       - Open **Settings** (Gear Icon on the left).
       - Open **Security Tab**.
       - Click **"Backup"** (Backup seed).
       - Review to make sure they match your source wallet.
       - If they don’t match, **you missed a step**.
   - **Slow down** – this process should only take a couple of minutes, but if it's your first time, read each line carefully.
   - Follow the steps slowly and exactly, and you will **learn better** and **become more empowered** in understanding.

---

✅ **You're now all set with your migrated wallet!**

To remove Divi Desktop and Wallet files from the source Windows computer, now that you have migrated, follow this link.
[Nuke It!](https://github.com/7h3v01c3/tutorials/blob/main/nuke_it/divi/remove_divi_desktop.md)
