**# Ex.No.1    FTK Imager: A Forensic Imaging Tool Overview

## Acquiring Volatile Memory (RAM) Using FTK Imager
<br>


### Steps to Capture RAM Using FTK Imager
<br>

### 1. Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the FTK Imager icon and select **Run as administrator**.
<br>
<br>


![1000164287](https://github.com/user-attachments/assets/80ae0ff8-d0d9-4557-92e4-ba85c6fa431f)

<br>
<br>

### 2. Initiate Memory Capture
- In the top menu bar, click **File → Capture Memory...** from the dropdown list.
  <br>
<br>

  <img width="1920" height="1080" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/1a77b4ce-77c0-4c76-b67e-8e11d45d44b2" />
<br>
<br>

### 3. Configure Destination
A dialog box will appear where you configure where and how the memory will be saved.

- **Destination Path:**  
  Click **Browse** to select a folder on an **external drive** (not the system drive).  

- **Destination Filename:**  
  You can keep the default `memdump.mem` or assign a more descriptive name.

- **Optional: Include pagefile.sys**  
  Check this box to capture `pagefile.sys`, which is virtual memory stored on the disk.  
  > Note: This may increase capture size and duration, but can contain valuable artifacts.

- **Optional: Create AD1 file**  
  Saves the memory dump in an AccessData-specific container file.  
  > Generally not necessary if using tools like **Volatility** for analysis.



<br>
<br>

<img width="1920" height="1080" alt="Screenshot (2)" src="https://github.com/user-attachments/assets/fbae21ed-4a4e-4cbf-9b43-d5c57e1bd761" />


<br>
<br>

### 4. Start Capture
- Click the **Capture Memory** button to begin acquisition.
<br>
<br>

<img width="1920" height="1080" alt="Screenshot (3)" src="https://github.com/user-attachments/assets/2e208884-fc94-4f08-94db-80796aea2ab0" />

<br>
<br>

### 5. Wait for Completion
- A progress bar will indicate the capture status.  
- Capture time depends on the system’s RAM size.  
- Once finished, the memory dump file will be available in the destination folder.
---
<br>
<br>

## Acquiring Non-Volatile Memory (Disk Image) Using FTK Imager


### 1. Start the Process
- In FTK Imager, go to the top menu bar: **File → Create Disk Image...**.

<br>
<br>
<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/dfdd9e32-dcbc-444c-8ac8-0256b3901e3e" />

<br>

### 2. Select Source Evidence Type
A window will appear asking you to choose the source type:

- **Physical Drive:** Images the entire disk, including all partitions, unallocated space, and the Master Boot Record (MBR).  
- **Logical Drive:** Images a specific partition (e.g., C: drive).  
- **Image File:** Converts or copies an existing image file.  
- **Contents of a Folder:** Creates an image of a specific folder only.  

> **Tip:** For full forensic imaging, select **Physical Drive**.
<br>
<br>
<p align="center">

<img width="1920" height="1080" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/4d4254f7-4305-4be3-ac85-fdbe9e37a00f" />

</p>
<br>
<br>

### 3. Select the Source Drive
- From the dropdown, choose the physical drive to image (connected via **write-blocker**).  
- Click **Finish**.
 <br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/daa3080b-bfed-470b-a34d-cb1e28794afb" />
</p>
<br>
<br>

### 4. Configure the Image Destination
- Click **Add...** in the "Create Image" window to define the image **format** and **destination**.
  <br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (7)" src="https://github.com/user-attachments/assets/2515ab32-8ecd-4200-8b31-b0840cde46f8" />

<br>

#### Options:

- **Image Type:**  
  - **E01 (EnCase Format):** Recommended; includes compression, metadata, and error-checking.  
  - **Raw (DD):** Bit-for-bit copy with no extra features.
<br>
<br>
<p align="center">
<img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/2a4b8ef6-8e50-4571-b794-8c59f1d5b3a3" />

</p>
<br>
<br>

- **Fill in Evidence Item Information:**  
  - Enter case details, examiner name, and description.  
  - This information is stored in the image metadata (important for documentation).
 <p align="center">
<img width="1920" height="1080" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/c034d06e-3d7a-4460-b5f1-e3a2cf1a25f6" />

</p>
<br>
<br>

- **Choose Destination Folder:**  
  - Must be a different drive from the source.  
  - Name the image file (e.g., `Case001_SuspectHDD`).  

- **Image Fragment Size:**  
  - Set a value to split the image into multiple parts.  
  - Set to `0` for a single image file.
  <br>
  <br>
  
<p align="center">
<img width="1920" height="1080" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/0c2ca1d6-29ad-424b-b13c-abe05e7dee07" />

</p>
<br>
<br>


### 5. Start the Imaging Process
- Click **Finish** to return to the "Create Image" screen.  
- **Check "Verify images after they are created"** to calculate hash values and ensure integrity.  
- Click **Start**.
  <br>
  <br>
  <p align="center">
  <img width="300"  alt="image" src="https://github.com/user-attachments/assets/739045f1-11bc-474a-9343-2e9aa19ec376" />
  <img width="300"alt="image" src="https://github.com/user-attachments/assets/7bef2114-0017-4a7b-9e19-0f356c3e3236" />
</p>
<br>
<br>

### 6. Completion and Hash Verification
- The imaging process may take time depending on the drive size.  
- After completion, FTK Imager verifies the hashes automatically.  
- A final window shows **MD5** and **SHA1** hashes for both the source drive and image.  
- Matching hashes confirm the forensic image’s integrity.

