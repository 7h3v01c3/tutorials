### Bypassing the Daemon Check on Manual Install (Windows)

To disable the daemon version check on a manual install of the Divi daemon in Windows, follow these **careful steps**. It's very important to **NOT accidentally add a file extension** like `.txt` when saving the file. Pay close attention!

#### Steps:
1. **Press the Windows key + R** to open the **Run** dialog box.
2. In the Run box, type:
   ```
   %appdata%
   ```
   Then click **OK**. This will open a folder called **Roaming** in File Explorer.
3. Inside the **Roaming** folder, look for and open the **Divi Desktop** folder (not **DIVI**).
4. Find the file named **Settings**. **Right-click** on it and select **Open with** → **Notepad**.
5. In the **Notepad** window, add the following line at the bottom of the file:
   ```
   daemon-version-check=disabled
   ```

#### **VERY IMPORTANT WHEN SAVING:**
- When you go to **Save** the file, **do not let Notepad add any file extensions!**
- To prevent this, when the **Save As** window opens:
   - **Change the "Save as type"** option at the bottom from **Text Documents (.txt)** to **All Files**.
   - Make sure the file is named exactly **Settings** (with **no additional extensions like `.txt`**).
   
**If you save it as `Settings.txt`, the change won’t work!**

6. After saving, double-check that the file is still named **Settings**, **not** **Settings.txt** or anything else. If it has any file extension, the daemon bypass will not work.

---

#### Important Paths:
- The full path to the **Settings** file is usually:
  ```
  C:\Users\{yourusername}\AppData\Roaming\Divi Desktop\Settings
  ```
