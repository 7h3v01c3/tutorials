(Windows) How to do a proper manual backup of your wallet files.
Backup Divi Desktop Wallet to USB Stick or Drive (Windows 10 & 11)
⚙️ What You’ll Need:

    ✅ One USB stick or external hard drive with at least 1 GB of free space

    ✅  A few minutes and focus—you’re backing up your wallet files.

    ✅  Store the backup somewhere safe and secure.


A secure, offline USB backup (preferably with duplicates) gives you a “frozen-in-time” copy of your wallet for easy migration, crash protection, and faster recovery than seed phrases alone—which, while mandatory, can take extra time or effort—making a USB backup a real time- and headache-saver. 



    Before You Begin: Prepare Your Backup Drive

    Insert your USB stick or external hard drive.
    (Note: Your USB drive may have a different name and show a different drive letter. The example below is for illustration only.)
    Create a dedicated folder for Divi backups, for example:

    DIVI-BACKUP

    Inside that folder, create a subfolder with the current month and year, for example:

    July-2027


    Your folder structure should look like this:

 USB:\ 
   └── DIVI-BACKUP\ 
            └── July-2027\ 


You will be placing the copies of your wallet files and folders (from the steps below) into the Month-Year folder. 
Six (6) Simple Steps
1. Exit Divi Desktop Wallet Completely

Do not minimize it—make sure it is fully closed.
Click X to close Divi Desktop Wallet and select Exit to close the application completely.

2. Open the Run Box

Press Windows Key + R on your keyboard simultaneously.
This opens the Run window.

3. Enter This Command and Click OK or Press Enter:

%appdata%

This takes you directly to the AppData Roaming folder.

4. Find and Open the Folder Named DIVI

    NOT Divi Desktop
    You're looking for the folder just named DIVI.

5. Inside the DIVI Folder, Locate and COPY These Items:

    wallet.dat (this holds your actual wallet data)

    backups (folder of auto-generated backups)

    monthlyBackups (longer-term backups)

Important: Do not move them—only copy.

6. Paste into Your Prepared Folder on the USB Drive 

Example path:

USB:\DIVI-BACKUP\July-2027\

Paste all three (3) items into that folder.

✅ That’s It! You’ve Backed Up Your Wallet

    Keep this USB backup safe and stored offline.

    If your PC crashes or you migrate to another machine, or you lose your seed words, this is your lifeline.
    This is a "Satoshi Backup"

Final Reminder

If you lose your wallet files or seed words, you lose access to your Divi.
Backups aren't optional—they're your responsibility. There’s no reset button.
