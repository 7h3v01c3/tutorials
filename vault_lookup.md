# Identify Your Divi Vault(s) in Debug Console

How to lookup your Divi Vault(s) and view fund allocations in **Divi Desktop** using the **Debug Console**.
This tutorial will walk you through identifying your Divi Vault Special Smart Contracts (DVSSC).

---

## Step 1: Enable Advanced Mode in Divi Desktop  

Before using the Debug Console, you need to enable **Advanced Mode** in Divi Desktop.  

1. **Open Divi Desktop** and allow it to **fully sync**.  
2. Click on the **Settings Icon (gear icon)** on the left panel.  
3. In **Settings**, stay on the **General Tab** (this is the default starting tab).  
4. Locate **Advanced Mode** and **check the box** to enable it.  

Once **Advanced Mode** is enabled, you’ll see a **Debug Console icon** appear in the top right corner of the application, just to the left of the staking slider.  

---

## Step 2: Access the Debug Console  

1. Click the **Debug Console (console icon)** in the top right corner.  
2. The console will require you to **unlock** it.  
   - **Tip:** Set an unlock time of **a couple of minutes**—this is enough time to run commands without needing to re-enter your password.  
   - If it locks before you're finished, simply **close the console, reopen it, and unlock it again.**  

---

## Step 3: Run the Simple Command to Check Vaults  

For a quick and **easy way** to check your **total vaulted, stakable, and spendable balance**, enter this command in the Debug Console:

```sh
getcoinavailability
```

The output will look something like this:

```json
{
  "Vaulted": 501,
  "Stakable": 56609.1543816,
  "Spendable": 56609.1543816
}
```

### How to Read the Output  

- **"Vaulted"** → This is the amount stored inside a **Divi Vault Special Smart Contract (DVSSC)**.  
- **"Stakable"** → This shows your coins that are **eligible for local staking** but are **not vaulted**.  
- **"Spendable"** → This is the balance you can freely **send or use** at any time.  

#### Verifying Your Balance  
If you add **Vaulted** and **Spendable** together, the sum should match your **total balance** displayed in your **Divi Desktop Wallet Overview**.

---

## Step 4: Advanced - Digging Deeper with Vault Details  

If you want **more details** about your vault—including **transaction IDs (TXIDs)** that are part of it—run the following command:  

```sh
getcoinavailability true
```

This will return **technical information** about your vault, including each individual **vault, value, and transaction IDs (TXIDs)**.

### Example Output:
```json
{
  "Vaulted": {
    "AllVaults": [
      {
        "vault": "D7hHqCYV4hL73gmvA8YVpmvEBcCxG8TT1E:DK4meuJcJWKew2SLCJxEptB3HwvszXvbFK",
        "value": 1000000,
        "txids": [
          "245638dbbe5dbdeabd5d8428e688a09ee0f9a128d2e693f3ad4ac825ea2c3e64",
          "ffac5f3e3d693d5c86a8e500409feda36348c1c4ccfe0341a1b25042d31a62b8",
          "73394ff41ef57c9c022ea9d8eaf9868daff2c0fa932df27b5a662700d0a46afc",
        ]
      },
      {
        "vault": "DCEwUMRW8FZJs8R18KDAVtHi1X4mKmaiTX:DDeL1nSGWnWYXrRPcomS4d3pk9RWg2MR18",
        "value": 138176.99977250,
        "txids": [
          "761c635af38ddc68cd9d60cb6ef5a8430149f92e2127a4ac06bd1bcf74bad1a4",
          "2701bc95ff71652655b9b7b3487d3af28a7d4be9561e0b5396cf12b928dd5a1d",
          "7a2e6a1a94dbfc874794fab86ec8f9a3065780e3318ff366de28d0202c13273a"
        ]
      }
    ],
    "NonVaults": 0
  },
  "Stakable": {
    "AllVaults": [],
    "NonVaults": 57109.1544067
  },
  "Spendable": {
    "AllVaults": [],
    "NonVaults": 57109.1544067
  }
}
```

### **Understanding the Vault Details**
Each vault is displayed in top `"AllVaults"` and contains:  

- **"vault"** → This is the Vault Name as is recorded on the blockchain. You may have more than one vault, and each will have a unique key pair identified in "vault".
- **"value"** → This is the **total amount stored in the vault**.  
- **"txids"** → A list of **transaction IDs (TXIDs)** linked to the vaulted funds. If you have multiple vaults, there will be **multiple vault entries** in `"AllVaults"`.

#### **Checking Your Vault Balances**
1. **If you only want to know if you have vaulted funds**, just use `getcoinavailability`.  
2. **If you want full vault details**, including individual TXIDs, use `getcoinavailability true`.

---

## Final Notes  

- **If "Vaulted" shows a balance greater than 0**, this means your funds are still in a vault and working inside a **Divi Vault Special Smart Contract**.  
- **If "Vaulted" is 0**, your funds are either **stakable or fully spendable**.  
- **Checking for a vault first is key**: Many users assume they still have funds stuck when in reality, they are always soveriegnly in control.  

---

## What If You Need Further Help?  

If you’re still unsure about your vault status or next steps, you can:  

- **Join the Divi Project Telegram** for lite support and discussions:  
  👉 [Divi Telegram](https://telegram.diviproject.org)  

- **Join the Divi Project Discord** for real-time support and discussions:  
  👉 [Divi Discord](https://discord.diviproject.org)  

- **Consult TheVoice for personalized guidance**:  
  👉 [Schedule with TheVoice](https://www.cal.com/thevoice)  

---
💡 **If this tutorial helped you, consider supporting the author.** All guides are created through voluntary effort — your donation keeps them coming. 👉 [Support here](https://www.thevoice.dev/#donations)

## 🚀 Take Control of Your Vaults
By following these steps, you’ll **know exactly where your funds are and what they are doing**.  
Taking the time to familiarize yourself with these tools will help you **manage your Divi assets with confidence**.
