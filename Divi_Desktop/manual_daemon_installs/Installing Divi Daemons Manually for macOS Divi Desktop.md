### Tutorial: Installing Divi Daemons Manually for macOS Divi Desktop

#### Step 1: Download the Divi Daemon Files
Download the Divi daemon files from the official GitHub repository.

**Using Terminal:**
1. Open **Terminal** and run this command to download the daemon tarball:
   ```bash
   wget https://github.com/DiviProject/Divi/releases/download/v3.0.0/divi-3.0.0-osx64-9e2f76c.tar.gz
   ```

#### Step 2: Extract the Tarball
**Using Terminal:**
1. Once the download is complete, extract the tarball with:
   ```bash
   tar -xzvf divi-3.0.0-osx64-9e2f76c.tar.gz
   ```

This will extract the Divi daemons (`divid`, `divi-cli`, `divi-tx`) into the `divi-3.0.0/bin` directory.

#### Step 3: Create the Correct Directory Structure

You need to make sure the directory `divid/unpacked/divi_osx` exists inside the **Divi Desktop** folder.

**Using Terminal:**
1. Run the following command to create the necessary directories:
   ```bash
   mkdir -p ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx
   ```

**Using Finder + Go:**
1. Open **Finder**.
2. In the **Menu Bar**, click **Go** → **Go to Folder**.
3. Enter the following path and click **Go**:
   ```
   ~/Library/Application Support/Divi Desktop/
   ```
4. Inside the **Divi Desktop** folder, if the `divid/unpacked/divi_osx` folder doesn't exist, manually create it:
   - Right-click and select **New Folder**, name it **divid**.
   - Inside the **divid** folder, create another folder called **unpacked**.
   - Inside the **unpacked** folder, create a final folder called **divi_osx**.

#### Step 4: Move Daemons to the Correct Location

**Using Terminal:**
1. Run this command to move the extracted daemons (`divid`, `divi-cli`, `divi-tx`) to the newly created directory:
   ```bash
   mv divi-3.0.0/bin/* ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx/
   ```

**Using Finder + Go:**
1. In **Finder**, navigate to where the downloaded and extracted files are located (likely in **Downloads** or wherever you extracted the tarball).
2. Open the `divi-3.0.0/bin` folder.
3. Copy the files `divid`, `divi-cli`, and `divi-tx`.
4. Paste them into the `divid/unpacked/divi_osx` folder inside `Divi Desktop`.

#### Step 5: Set Correct Permissions

**Using Terminal:**
1. Navigate to the `divi_osx` directory:
   ```bash
   cd ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx/
   ```

2. Set the proper permissions so the files can be executed:
   ```bash
   chmod g+rwx divid divi-cli divi-tx
   ```

**Using Finder + Get Info:**
1. In **Finder**, right-click on each of the daemon files (`divid`, `divi-cli`, `divi-tx`), and select **Get Info**.
2. Under the **Sharing & Permissions** section, make sure you have **Read & Write** permissions.

#### Step 6: Verify Daemons Are Installed Correctly

**Using Terminal:**
1. To verify that the daemons are installed correctly, run the following commands:
   ```bash
   ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx/divid --version
   ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx/divi-cli --version
   ~/Library/Application\ Support/Divi\ Desktop/divid/unpacked/divi_osx/divi-tx --version
   ```

**Using Finder + Terminal:**
1. Open **Finder** and navigate to:
   ```
   ~/Library/Application Support/Divi Desktop/divid/unpacked/divi_osx/
   ```
2. Drag and drop each daemon (`divid`, `divi-cli`, `divi-tx`) into a **Terminal** window and press **Enter** after each to check if they display the version information.

If the commands respond with version information, the installation is complete, and the daemons are ready for use.

---

#### Recap: Key Paths for macOS Divi Desktop Daemon Installation

- **Daemons should be placed in**:
  ```
  ~/Library/Application Support/Divi Desktop/divid/unpacked/divi_osx/
  ```
- **Daemons to move**:
  - `divid`
  - `divi-cli`
  - `divi-tx`

Ensure the directory structure is correct before moving the daemons, and that all files have proper permissions for execution.
