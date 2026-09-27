# How to Manually Back Up Your Divi Wallet Files on Windows

## Backup Divi Desktop Wallet to a USB Stick or External Drive

**Applies to:** Windows 10 and Windows 11

---

## What You’ll Need

* One USB stick or external hard drive with at least **1 GB of free space**
* A few minutes of focus
* A safe and secure place to store your backup

A secure offline USB backup, preferably with duplicates, gives you a “frozen-in-time” copy of your wallet files. This can help with easy migration, crash protection, and faster recovery than seed phrases alone.

Seed phrases are still mandatory, but restoring from them can sometimes take extra time or effort. A USB backup can save you time and frustration.

---

## Before You Begin: Prepare Your Backup Drive

1. Insert your USB stick or external hard drive.

   > **Note:** Your USB drive may have a different name and drive letter. The examples below are for illustration only.

2. Create a dedicated folder for Divi backups, for example:

   ```text
   DIVI-BACKUP
   ```

3. Inside that folder, create a subfolder using the current month and year, for example:

   ```text
   July-2027
   ```

Your folder structure should look like this:

```text
USB:\
└── DIVI-BACKUP\
    └── July-2027\
```

You will copy your wallet files and folders into the `Month-Year` folder.

Example:

```text
USB:\DIVI-BACKUP\July-2027\
```

---

# Six Simple Steps

## 1. Exit Divi Desktop Wallet Completely

Do not minimize the wallet.

Click the **X** to close Divi Desktop Wallet, then select **Exit** to close the application completely.

---

## 2. Open the Run Box

Press the following keys at the same time:

```text
Windows Key + R
```

This opens the **Run** window.

---

## 3. Enter the AppData Command

In the Run window, enter:

```text
%appdata%
```

Then click **OK** or press **Enter**.

This takes you directly to the **AppData Roaming** folder.

---

### Keep These Tutorials Going

These tutorials are freely shared to help others learn, solve problems, and pass that knowledge on.

**[If this helped you, consider supporting the work and helping keep these tutorials going →](https://thevoice.dev/#donations)**

## 4. Find and Open the `DIVI` Folder

Look for the folder named:

```text
DIVI
```

> **Important:** Do not open the folder named `Divi Desktop`.
> You are looking for the folder named exactly `DIVI`.

---

## 5. Copy the Required Wallet Files and Folders

Inside the `DIVI` folder, locate and **copy** the following three items:

```text
wallet.dat
backups
monthlyBackups
```

### What These Items Are

* `wallet.dat` — holds your actual wallet data
* `backups` — contains auto-generated wallet backups
* `monthlyBackups` — contains longer-term backups

> **Important:** Do not move these items. Only copy them.

---

## 6. Paste the Files into Your USB Backup Folder

Paste all three items into your prepared backup folder on the USB drive.

Example path:

```text
USB:\DIVI-BACKUP\July-2027\
```

You should now have copies of these items in that folder:

```text
USB:\DIVI-BACKUP\July-2027\
├── wallet.dat
├── backups\
└── monthlyBackups\
```

---

# Backup Complete

You have now backed up your Divi wallet files.

Keep this USB backup safe and stored offline.

If your PC crashes, you migrate to another machine, or you lose your seed words, this backup may be your lifeline.

This is your **Satoshi Backup**.

---

# Final Reminder

If you lose your wallet files or seed words, you may lose access to your Divi.

Backups are not optional. They are your responsibility.

There is no reset button.
