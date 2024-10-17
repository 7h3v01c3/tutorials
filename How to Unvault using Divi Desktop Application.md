# Unvaulting Funds from Divi Vault: Step-by-Step Guide

## Preparation

1. **Open a Text Editor**:
   - On **Windows**, press `Ctrl + Space` and search for **Notepad**.
   - On **macOS**, press `Cmd + Space` and search for **TextEdit**.

2. **Create and Save the Document**:
   - Name the file **"unvault"** and save it on your **Desktop** for easy access.

## Setting Up Divi Desktop

3. **Launch Divi Desktop**:
   - Ensure your wallet is **fully synchronized**.

4. **Enable Advanced Mode**:
   - If the **Debug Console** isn't visible in the top right corner of the Divi Desktop Application, go to **Settings**, check the box for **Advanced Mode**, and then open the **Debug Console**.

5. **Unlock Your Wallet**:
   - You’ll need to unlock the wallet to proceed. Select a timeout duration that suits your session length.

## Generating an Address and Checking Coin Availability

6. **Generate a New Receiving Address**:
   - In the **Debug Console**, enter the following command on the command line and press Enter:
     ```bash
     getnewaddress
     ```
   - This command will produce a **new receiving address**. To copy the address:
     1. **Highlight the address** with your mouse by clicking and dragging over the entire address in the console.
     2. Copy the highlighted address:
        - **Windows**: `Ctrl + C`
        - **macOS**: `Cmd + C`

7. **Save the Address to Your Document**:
   - Open the **"unvault"** document you created earlier. **Paste the address from Step 6** into this document:
     - **Windows**: `Ctrl + V`
     - **macOS**: `Cmd + V`
   - Save the document using `Ctrl + S` (Windows) or `Cmd + S` (macOS).

8. **Check UTXO Availability**:
   - In the **Debug Console**, enter the following command on the command line and press Enter:
     ```bash
     getcoinavailability true
     ```
   - Scroll through the output to locate **Vaulted** UTXOs. If you have over **500 UTXOs**, consider performing two separate unvaulting transactions.

## Executing Transactions

### Conduct a Test Transaction

9. **Retrieve and Copy the Address**:
   - Open your **"unvault"** document from the Desktop.
   - Find the **address saved from Step 6** and **copy it**:
     - **Windows**: `Ctrl + C`
     - **macOS**: `Cmd + C`

10. **Run a Small Test Transaction**:
   - In the **Debug Console**, paste the address into the following command on the command line, replacing `<your_address_from_unvault_document>` with the address you copied, then press Enter:
     ```bash
     reclaimvaultfunds <your_address_from_unvault_document> 1
     ```
   - Paste the address by:
     - **Windows**: `Ctrl + V`
     - **macOS**: `Cmd + V`
   - **Double-check** the pasted address for accuracy before hitting Enter.

11. **Confirm Transaction**:
   - Navigate to the **Overview** tab to verify if the transaction is **awaiting confirmations**.

### Unvault the Full Amount

- **For vaults under 5 million DIVI**:
  - In the **Debug Console**, enter the following command on the command line to unvault the entire amount, replacing `<your_address_from_unvault_document>` with the address copied from your **unvault document**:
    ```bash
    reclaimvaultfunds <your_address_from_unvault_document> fullamount "sweep_funds"
    ```
    - Paste the address:
      - **Windows**: `Ctrl + V`
      - **macOS**: `Cmd + V`
    - **Confirm the accuracy** of the pasted address before executing the transaction.
  
  - **Important Note**: The `"sweep_funds"` option will move **all available funds** to the address from Step 6, regardless of the specific amount you input. For example, you can simply enter:
    ```bash
    reclaimvaultfunds <your_address_from_unvault_document> 1 "sweep_funds"
    ```
    - This command will **sweep** everything in the vault to the specified address, making `"sweep_funds"` very powerful.

- **For vaults of 5 million DIVI or larger**:
  - Due to the likelihood of needing two transactions, proceed with a split approach:
    1. **Step 1**: In the **Debug Console**, enter the following command on the command line to unvault a portion of the funds, then press Enter:
       ```bash
       reclaimvaultfunds <your_address_from_unvault_document> 5000000
       ```
       - Paste the **address** as needed:
         - **Windows**: `Ctrl + V`
         - **macOS**: `Cmd + V`
    
    2. **Step 2**: Complete the process by sweeping the remaining funds with the following command, then press Enter:
       ```bash
       reclaimvaultfunds <your_address_from_unvault_document> remaining_amount "sweep_funds"
       ```
     - Ensure you **double-check the pasted address** at each step for accuracy.
     - Like in the previous example, `"sweep_funds"` will transfer all remaining funds in the vault to the specified address.

## Quick Command Reference

- **General Command Reference**:
  - `help` – Displays a list of general commands.
  - `getcoinavailability true` – Provides details on available UTXOs.
  - `reclaimvaultfunds <address_from_unvault_document> <amount> ["sweep_funds"]` – Unvaults specified amounts. Use `"sweep_funds"` to move all available funds to the address.
