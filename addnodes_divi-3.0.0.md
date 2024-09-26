**How to Manually Add Nodes in Divi Desktop – Windows Tutorial**

Hi everyone! In today’s tutorial, I’ll walk you through the process of manually adding nodes to the Divi Desktop wallet using Notepad. This is a temporary fix for those experiencing syncing issues . Let’s get started!

### Step 1: Create a New Notepad Document

1. **Open Notepad** on your Windows computer.
2. **Save the file** as `addnodes.txt`. 
   - You can save this file anywhere for now, just make sure you can find it later.

3. **Add the following line at the top** of the document:
   ```
   syncnodes=0
   ```

This step stops adding nodes automatically and allows us to manually input the decentralized network of needed peers.

---

### Step 2: Get the List of Active Nodes

Now we need to gather the latest list of active nodes from Divi’s blockchain explorer. Here’s how:

1. **Open your web browser** and go to [Divi Explorer on CryptoID](https://chainz.cryptoid.info/divi/).
   
2. On that page, navigate to the **Network section**. You can also go directly to this link:  
   [Divi Network Info](https://chainz.cryptoid.info/divi/#!network).

3. Look for **Divi Core 3.0.0.0** and select the **"Node List"** option.

4. This will display a list of active nodes seen in the last 24 hours. 

5. **Copy the entire node list** by highlighting it, then right-click and select "Copy."

---

### Step 3: Add Nodes to Your Text File

1. Go back to your `addnodes.txt` file. 
   
2. **Paste the list** of nodes you just copied under the line `syncnodes=0`.  
   Make sure each node is on its own line. Here’s an example of how it should look:

   ```
   syncnodes=0
   addnode=IPADDRESS1
   addnode=IPADDRESS2
   addnode=IPADDRESS3
   ```

3. **Save** your `addnodes.txt` file.

---

### Step 4: Modify the `divi.conf` File

1. Press the **Windows Key + R** to open the "Run" dialog box.

2. In the Run box, type:
   ```
   %appdata%
   ```
   and press **Enter**.

3. Find and open the folder named **DIVI**.

4. Inside this folder, locate the file called `divi.conf` and **open it with Notepad**.

5. Once open, **remove all existing addnode entries** from the file.

6. Go back to your `addnodes.txt` file, **copy everything**, and then paste it into your `divi.conf` under the `## mndiviaddress` section.

7. Save and close the `divi.conf` file.

---

### Step 5: Start Divi Desktop

1. Now, start the **Divi Desktop Application**.
   
2. The app will automatically start the daemon, load the block index, and begin syncing. After a short while, it will load the new peers list we just added.

And that’s it! After this process, your wallet should be syncing with the correct nodes, and you’ll be back on track.

---

**Wrap Up**

If you found this tutorial helpful, don’t forget to like and subscribe for more Divi tips and tricks.

As always thanks for watching!
