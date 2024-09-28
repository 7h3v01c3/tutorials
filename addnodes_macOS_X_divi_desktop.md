**How to Manually Add Nodes in Divi Desktop – macOS X Tutorial**

*Make sure the Divi Desktop Application is closed before starting.*

Hi everyone! In today’s tutorial, I’ll guide you through manually adding nodes to the Divi Desktop wallet using TextEdit on macOS. This is a temporary fix for those experiencing syncing issues. Let’s dive in!

### Step 1: Create a New TextEdit Document

1. **Open TextEdit** on your Mac.
   - You can find it by searching for “TextEdit” in Spotlight (Command + Space).
   
2. **Create a new document** and ensure the format is set to plain text. You can do this by going to **Format > Make Plain Text**.

3. **Save the file** as `addnodes.txt`.  
   - Save it somewhere easy to find, like your Desktop.

4. **Add the following line at the top** of the document:
   ```
   syncnodes=0
   ```

This command temporarily disables automatic node addition and allows you to manually input peers.

---

### Step 2: Get the List of Active Nodes

Now, let’s gather the latest list of active nodes from Divi’s blockchain explorer. Here’s how:

1. **Open your web browser** and navigate to [Divi Explorer on CryptoID](https://chainz.cryptoid.info/divi/).

2. Go to the **Network section**. Alternatively, you can use this direct link:  
   [Divi Network Info](https://chainz.cryptoid.info/divi/#!network).

3. Look for **Divi Core 3.0.0.0** and select the **"Node List"** option.

4. This will show a list of active nodes from the last 24 hours.

5. **Copy the entire node list** by highlighting it, then right-click and select "Copy."

---

### Step 3: Add Nodes to Your Text File

1. Go back to the `addnodes.txt` file in TextEdit.

2. **Paste the list of nodes** you copied below the line `syncnodes=0`.  
   Make sure each node appears on its own line, like this:

   ```
   syncnodes=0
   addnode=IPADDRESS1
   addnode=IPADDRESS2
   addnode=IPADDRESS3
   ```

3. **Save** the `addnodes.txt` file.

---

### Step 4: Modify the `divi.conf` File

1. Open **Finder**, then in the top menu, click **Go** and select **Go to Folder**.

2. In the dialog box, enter:
   ```
   ~/Library/Application Support/DIVI
   ```
   and click **Go**.

3. Inside this folder, locate the file called `divi.conf` and **open it with TextEdit**.

4. Once open, **remove any existing addnode entries** from the file.

5. Go back to your `addnodes.txt` file, **copy everything**, and then paste it into your `divi.conf` file under any previous addnodes section.

6. Save and close the `divi.conf` file.

---

### Step 5: Start Divi Desktop

1. Now, open the **Divi Desktop Application**.

2. The app will automatically start the daemon, load the block index, and begin syncing. After a short while, it will load the new peers list that we just added.

And that’s it! After completing these steps, your wallet should sync with the correct nodes, getting you back on track quickly.

---

**Wrap Up**

If you found this tutorial helpful, don’t forget to like and subscribe for more Divi tips and tricks. Thanks for watching!
