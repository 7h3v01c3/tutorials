### Bypassing the Daemon Check on Manual Install (Linux)

To disable the daemon version, check on a manual install of the Divi daemon by following these steps:

#### Option 1: Using the Terminal
1. Open the terminal.
2. Type the following command to open the settings file:
   ```bash
   nano ~/.config/divi-desktop/Settings
   ```
3. In the settings file, add the following line:
   ```
   daemon-version-check=disabled
   ```
4. Save the file (`Ctrl + O`), then exit (`Ctrl + X`).

#### Option 2: Using the Files GUI
1. Navigate to `.config/divi-desktop` in your file explorer.
2. Right-click on the **Settings** file and select **Open with Text Editor**.
3. Add the following line to the file:
   ```
   daemon-version-check=disabled
   ```
4. Save the file.

---

#### Important Paths:
- **Full path to the settings file:**
  ```
  /home/{yourusername}/.config/divi-desktop/Settings
  ```
- **Path to the Divi daemon folder:**
  ```
  ~/.config/divi-desktop/divid/unpacked/divi_ubuntu
  ```
or
- **Full path to the daemons:**

  ```
 /home/{yourusername}/.config/divi-desktop/divid/unpacked/divi_ubuntu
  ```
  This folder should contain:
  `divid`
  `divi-tx`
  `divi-cli`

---
