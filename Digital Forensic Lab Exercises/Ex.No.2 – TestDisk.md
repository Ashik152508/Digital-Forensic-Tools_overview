#  Ex.No.2    TestDisk: Open-Source Data Recovery Tool

## Aim :
To use TestDisk step by step to recover a missing partition and repair a corrupted one.



## 🛠️ Installation
Linux (Debian/Ubuntu): sudo apt-get install testdisk

macOS (Homebrew): brew install testdisk

Windows: Download the executable from the official CGSecurity website.

## Procedure

### 1. Create a Log File
- Launch TestDisk from your terminal or command prompt using sudo testdisk (or testdisk_win.exe on Windows).

- Select the [Create] option to generate a log file of the recovery session. This is helpful for future reference or troubleshooting.
<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/b3173f11-9578-4cb3-b59e-f09b8eb38174" />

</p>
<br>
<br>

### 2. Select the Drive to Analyze
- TestDisk will display a list of all detected storage devices.

- Use the Up/Down arrow keys to highlight the drive that contains your lost data.

<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/6996b1b8-1d8d-4c43-8aae-9345dfa3805a" />

</p>
<br>
<br>

- Select [Proceed] to move to the next step.

### 3. Choose the Partition Table Type
- TestDisk will automatically suggest the most likely partition table type (e.g., Intel/PC, EFI GPT).

- The default value is usually correct. Confirm the selection by pressing Enter.
<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/234e5d69-f233-4609-b908-e344b6cdcaf0" />
</p>
<br>
<br>

### 4. Analyze Current Partition Structure
- From the main menu, choose [Analyse] and press Enter.
<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (15)" src="https://github.com/user-attachments/assets/9917256e-60d4-4f2b-9d81-cd1f796138b5" />

</p>
<br>
<br>

- This will display the current partition table and check for errors or missing partitions.

### 5. Perform a Quick Search
- After the analysis, you will be prompted to perform a [Quick Search].

<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (16)" src="https://github.com/user-attachments/assets/b34ce1d0-616b-4560-8014-5a2a9b7080e2" />

</p>
<br>
<br>

- Select it and press Enter to scan the drive for lost partitions.

- Once a partition is found, you can press p to list its files. Deleted files and folders often appear in red.

- Press q to return to the search results.

  ### 6. Perform a Deeper Search
- If the Quick Search fails to find your lost partitions, select [Deeper Search].

-<br>
<br>
<p align="center"> 
<img width="1920" height="1080" alt="Screenshot (17)" src="https://github.com/user-attachments/assets/64e4a552-16cc-4ff1-897d-cf144ebbb8bf" />

</p>
<br>
<br>

- This process can take a long time, as it scans the entire drive, block by block, to find remnants of partition structures.

- Again, use p to preview files and confirm if a found partition is the one you are looking for.

### 7. Modify Partition Status
- After finding the correct partitions, use the Left/Right arrow keys to set their status.

- Use **Left/Right arrow keys** to change status:  
  - **P**: Primary  
  - ***:** Bootable  
  - **L**: Logical  
  - **D**: Deleted

    <br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (18)" src="https://github.com/user-attachments/assets/4b4ef169-5011-4168-9e45-2d6c20cb3bff" />
</p>
<br>
<br>

- Ensure that the partitions you want to recover are marked as Primary or Logical (and not deleted).

### 8. Write the Partition Table
- Once you are confident the partition structure is correct, select [Write] from the menu.

<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (19)" src="https://github.com/user-attachments/assets/06d120a7-2bf2-4d1c-a924-7d25913d3a55" />

</p>
<br>
<br>

- Confirm the operation by pressing y (for yes). This will write the new partition table to your disk.

<br>
<br>
<p align="center">
  <img width="1920" height="1080" alt="Screenshot (20)" src="https://github.com/user-attachments/assets/146bf17b-2cba-4b63-b9b3-7cb446b714ad" />

</p>
<br>
<br>


- WARNING: This is a permanent change. Double-check your selections before writing.

### 9. Recover Files
- If you just need to recover a few files without fixing the partition table, you can do so from the file list (after pressing p).

- Use the colon : key to select the files you want to recover.

- Press the uppercase C key to copy the selected file(s).

- Navigate to a safe destination on a different storage device and press uppercase C again to paste.

### 10. Exit and Restart
- If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.
- Once your task is complete, select [Quit] to exit the program.
