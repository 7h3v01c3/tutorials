### Bypassing the Daemon Check on Manual Install (macOS)

To disable the daemon version check on a manual install of the Divi daemon, follow these steps:

#### Option 1: Using Terminal
1. Open **Terminal**.
2. Enter the following command to open the settings file:
   ```bash
   nano ~/Library/Application\ Support/Divi\ Desktop/Settings
   ```
3. In the settings file, add the following line:
   ```
   daemon-version-check=disabled
   ```
4. Save the file (`Ctrl + O`), then exit (`Ctrl + X`).

#### Option 2: Using Finder and TextEdit
1. Open **Finder**.
2. From the menu bar, click **Go** → **Go to Folder**.
3. Enter the path:
   ```
   ~/Library/Application Support/Divi Desktop/
   ```
4. Locate the **Settings** file, right-click on it, and select **Open With** → **TextEdit**.
5. Add the following line to the file:
   ```
   daemon-version-check=disabled
   ```
6. Save the file.

---

#### Important Paths:
- **Full path to the settings file:**
  ```
  /Users/{yourusername}/Library/Application Support/Divi Desktop/Settings
  ```
- **Path to the Divi daemon folder:**
  ```
  ~/Library/Application Support/Divi Desktop/divid/unpacked/divi_macos
  ```
  This folder should contain:
  - `divid`
  - `divi-tx`
  - `divi-cli`

---
