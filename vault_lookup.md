# How to Identify Your Divi Vault(s) Using the Debug Console in Divi Desktop

If you are unsure whether your funds are **vaulted, stakable, or fully spendable**, you can check directly in **Divi Desktop** using the **Debug Console**.  
This guide will show you how to **view your Divi Vault Special Smart Contracts (DVSSC)** and understand the breakdown of your balances.

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

## Step 4 (Optional): Digging Deeper with a More Detailed Command  

If you want **more details** about your vault—including **transaction IDs (TXIDs)** that are part of it—run the following command:  

```sh
getcoinavailability true
```

This will return more **technical information** about your vault, including individual transactions that make up your **vaulted** balance. If you're interested in learning more, this is a great way to **become informed** and understand how Divi Vaults operate.

---

## Final Notes  

- **If "Vaulted" shows a balance greater than 0**, this means your funds are still in a vault and working inside a **Divi Vault Special Smart Contract.**  
- **If "Vaulted" is 0**, your funds are either **stakable or fully spendable**.  
- **Checking for a vault first is key**: Many users assume they still have funds stuck when in reality, they may already be vaulted.  

---

## What If You Need Further Help?  

If you’re still unsure about your vault status or next steps, you can:  

- **Join the Divi Project Telegram** for lite support and discussions:  
  👉 [Divi Telegram](https://telegram.diviproject.org)  

- **Join the Divi Project Discord** for real-time support and discussions:  
  👉 [Divi Discord](https://discord.diviproject.org)  

- **Consult TheVoice for personalized guidance**:  
  👉 [Schedule with TheVoice](https://www.cal.com/thevoice)  

This method ensures **you know exactly where your funds are and what they are doing.**  
Taking the time to familiarize yourself with these tools will help you manage your Divi assets more confidently. 🚀
