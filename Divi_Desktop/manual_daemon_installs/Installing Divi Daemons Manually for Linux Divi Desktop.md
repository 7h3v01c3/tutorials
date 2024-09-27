### Tutorial: Installing Divi Daemons Manually for Linux Divi Desktop

#### Step 1: Download the Divi Daemon Files
Download the Divi daemon files from the official GitHub repository:

1. Open a terminal and run the following command to download the tarball:
   ```bash
   wget https://github.com/DiviProject/Divi/releases/download/v3.0.0/divi-3.0.0-x86_64-linux-gnu-9e2f76c.tar.gz
   ```

#### Step 2: Extract the Tarball
Once downloaded, extract the contents of the tarball:

1. Run the following command in your terminal:
   ```bash
   tar -xzvf divi-3.0.0-x86_64-linux-gnu-9e2f76c.tar.gz
   ```

This will extract the Divi daemons (`divid`, `divi-cli`, `divi-tx`) into the current inside `divi-3.0.0/bin`

#### Step 3: Move Daemons to the Correct Location
Now, we need to move the daemons into the `.config/divi-desktop` directory in your home folder. Create the necessary directories, move the files, and ensure they're correctly nested.

1. First, create the necessary directory structure inside `.config/divi-desktop`:
   ```bash
   mkdir -p ~/.config/divi-desktop/divid/unpacked/divi_ubuntu
   ```

2. Move the extracted daemons (`divid`, `divi-cli`, and `divi-tx`) into the `divi_ubuntu` directory:
   ```bash
   mv divi-3.0.0/bin/divid ~/.config/divi-desktop/divid/unpacked/divi_ubuntu/
   mv divi-3.0.0/bin/divi-cli ~/.config/divi-desktop/divid/unpacked/divi_ubuntu/
   mv divi-3.0.0/bin/divi-tx ~/.config/divi-desktop/divid/unpacked/divi_ubuntu/
   ```

#### Step 4: Set Correct Permissions
You need to ensure the daemons have the correct permissions to execute. Run the following command to grant read, write, and execute permissions:

1. Navigate to the directory containing the daemons:
   ```bash
   cd ~/.config/divi-desktop/divid/unpacked/divi_ubuntu/
   ```

2. Grant the appropriate permissions:
   ```bash
   chmod g+rwx divid divi-cli divi-tx
   ```

#### Step 5: Verify Daemons Are Installed Correctly
To confirm the daemons are correctly installed and accessible:

1. Run the following commands to check:
   ```bash
   ./divid --version
   ./divi-cli --version
   ./divi-tx --version
   ```

If the daemons respond with version information, you're good to go!
