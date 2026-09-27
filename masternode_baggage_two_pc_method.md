# Why Your Reward is Not a Masternode Reward

Alright, let’s clear this up once and for all: the reward you’re seeing is **NOT** a masternode reward. Nope. Not even close. What you’re looking at is a staking reward tied to an address you once labeled something fancy like "Masternode [Name Here]" back in the good ol' masternode days.

Why does this happen? Because your **wallet file stores labels**. When your coins were used to **notarize the block, prove you’re at stake, and create the coinbase reward**, your wallet.dat file—has this address label and all related transactions are pointed to that labeled address. The Divi Desktop GUI takes this information and displays the proper on-chain balance for the new UTXO.

Now, let’s make this clearer:
- If you had **combined UTXOs (unspent transaction outputs)** in the past after dismantling your masternode, your DIVI would have moved to a **new address** within your wallet. But guess what? New addresses don’t have that fancy label. Why? Because you didn’t label them for a masternode.
- This isn’t a glitch or anything weird—it’s just how labels, wallet files, transactions/UTXOs, and the GUI work. And now you’ve learned something new!

---

## About That "Strange Value"

So, you’re looking at this reward and thinking, “Why is the amount strange?” Well, **it’s not strange.** It’s exactly what’s supposed to happen. Here’s why:

Divi operates using a **Hybrid Proof of Work/Proof of Stake UTXO-based consensus protocol.** The amount you see is correct because staking involves **notarizing**—which is the spending of a batch of your UTXOs (coins) to prove you’re at stake, and then sending them back to yourself with the newly minted coinbase reward added.

Here’s an example to make it crystal clear:

---

### Example: Staking with UTXOs
- Imagine you have a **10,000 DIVI UTXO** in your wallet.
- When staking, your your daemon used the 10,000 DIVI UTXO to create a hash, which **WON!** to compete for block validation.
- This UTXO that WON now needs to **PROVE** its ability to produce the matching hash, this is done during the notarization process - This is the **PROOF** of True PoS.
- If successful, it **sends the 10,000 DIVI back to you** (to the same address) and adds the staking reward—let’s say 581 DIVI—to the total.

So, on-chain, it looks like this:
**10581 DIVI** (your original 10,000 + the 581 reward)

Here’s what’s important to understand:
- **The original 10,000 DIVI didn’t disappear.** It was just temporarily used for work.
- **Your total balance only increases by the reward amount (581 DIVI in this case).**

This isn’t “strange.” It’s the blockchain doing what it’s supposed to do. The UTXOs are just the **engine under the hood** making staking happen.

---

## Why This Happens and Why It’s Brilliant

Divi’s staking process creates UTXOs every time it competes to mine a block. In doing so, it batches a portion of your funds to validate the network and secure the blockchain.

So no, your wallet isn’t broken—it’s doing exactly what it was designed to do. The next time you see one of these transactions, instead of scratching your head, click the **transaction link**. You’ll start to understand how Divi’s consensus system is a UTXO-based virtualized mining and why the daemon in divi has a highly modified Bitcoin Miner, with heritage related to Satoshi's Original miner, in the core code its called Divi Miner.

Congratulations—you’ve just leveled up your crypto knowledge. **Mind blown. 💥**

---

## Why You Should Consider Starting Fresh

Here’s where things get practical. If your wallet has **masternode baggage** (a.k.a. tons of irrelevant history and clutter), consider retiring your current wallet and starting fresh with a new 24-word seed phrase.

Why? Because sometimes it’s easier to declutter your blockchain closet than to live with the ghosts of masternodes past.

---

### Keep These Tutorials Going

These tutorials are freely shared to help others learn, solve problems, and pass that knowledge on.

**[If this helped you, consider supporting the work and helping keep these tutorials going →](https://thevoice.dev/#donations)**

## The “Mom” Method: Simple and Clean Migration

Let’s keep this simple: **this is just one way to migrate to a new wallet.** It’s designed for users who:
- Don’t want to mess with **console commands or terminal**.
- Prefer to avoid the hassle of creating and migrating wallet files manually.
- May not fully understand that **coins are on the blockchain, not your PC/MAC/LINUX or the APP itself**.

This is the easiest, most user-friendly method to create a new wallet and move on with life. It’s ideal if you want to simplify everything without diving into advanced options.

---

## Steps to Create a Pristine Wallet Without Masternode Baggage

### Step 1: Grab a Second Computer (Intermediate Machine)
1. **Install Divi Desktop Wallet** on the intermediate machine.
2. Generate a **new 24-word seed phrase** during setup.
   - Store it securely in a method that ensures long-term safety, restricted and secure access (not photographs or text files).
   - These 24 words are your new wallet—not the app, not the device, but the words.

### Step 2: Sync the New Wallet
- Let the wallet **sync fully with the blockchain**. Yes, it takes time, but shortcuts here lead to headaches later.

---

### Step 3: Transfer Funds to Your New Wallet
1. **From Your Primary Machine:**
   - Send a **test transaction** to the new wallet on the intermediate machine. Verify it works before sending everything.
   - Once confirmed, transfer the rest of your funds, effectively emptying the old wallet.
2. **On the Intermediate Machine:**
   - Your new wallet now holds all your funds. It’s clean, fresh, and free from masternode baggage. **You’re now living the minimalist crypto dream.**

---

### Step 4: Reset Your Primary Machine
1. **Uninstall Divi Desktop:**
   - Open Divi Desktop on your primary machine.
   - Go to **Settings** and enable **Advanced Mode** (check the box).
   - Navigate to the **Uninstall Tab** and click **Uninstall.**
2. **Reinstall Divi Desktop:**
   - Go to [https://diviproject.org/downloads](https://diviproject.org/downloads) and download the latest version.
   - During installation, select the option to **Recover Wallet** using the new 24-word seed phrase from the intermediate machine.
3. **Sync and Secure:**
   - Let the wallet **sync fully**.
   - Set a new password, and you’re good to go!

---

### Step 5: Clean Up the Intermediate Machine
1. **Uninstall Divi Desktop:**
   - Repeat the uninstall process from Step 4 (1), on the intermediate machine to remove Divi Desktop completely.

---

## Why This Matters

By following these steps, you:
- **Get a fresh wallet free from masternode clutter or unnecessary history.**
- **Learn how UTXOs work in staking, expanding your blockchain knowledge.**

### Remember:
1. **Your coins are on the blockchain, not in the app.**
2. **Your wallet is your seed phrase, not your device.**

So, embrace the process, enjoy the learning curve, and marvel at your newfound crypto expertise. You’re not just owning crypto—you’re understanding it to know how it helps with your freedom! 🚀
