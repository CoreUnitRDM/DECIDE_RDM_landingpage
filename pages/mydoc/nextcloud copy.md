---
title: "Using Nextcloud for Research Data Management"
keywords: Research Data Management, RDM, Cloud, Version control, Backup, Activity Log, Storage, Exchange, Rclone
last_updated: July 10, 2025
tags: [nextcloud, data management, cloud storage, würzburg university, rclone]
summary: Practical guide for using Nextcloud at Würzburg University for secure data storage, sharing, and integration with research workflows.
sidebar: decide_sidebar
permalink: nextcloud.html
folder: mydoc
---

Nextcloud is Würzburg University's secure cloud platform for managing and sharing research data. This guide gives you **step-by-step instructions** to get started, sync and share data, collaborate using Office, and even connect Nextcloud to external servers or analysis tools using `rclone`.

---

## 1. Registration and Login

### A. Register

No manual registration is needed. You can log in directly using your **University of Würzburg credentials**.

### B. Login

- Go to [https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/](https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/)


---

## 2. Upload and Download Files

### A. Upload via Browser

1. Log in via the web interface.
2. Click the **“+”** icon → **Upload File** or **Upload Folder**.
3. Or drag-and-drop files directly into the folder view.

### B. Download

1. Right-click on a file or folder.
2. Select **Download** to retrieve it as a ZIP or individual file.

---

## 3. Synchronize with the Desktop Client

### A. Install Nextcloud Client

- Download: [Nextcloud Clients](https://nextcloud.com/install/#install-clients)
- Supported: Windows, macOS, Linux, iOS, Android

### B. Configure

1. Open the installed client.
2. Enter your server:  
   `https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/`
3. Log in with your university credentials.
4. Select folders to sync.

> 💡 Tip: Enable selective sync for large datasets or different projects.

---

## 4. Share Data Securely

### A. Public Link

1. Click the **Share** icon next to a file or folder.
2. Select **Create public link**
   - Optionally set: password, expiration date, upload/download permissions

### B. Share with Team Members

1. In the **Share** box, type the username or email.
2. Choose permissions: view, edit, upload, or delete.

---

## 5. Customize File Access Rights

- Click the **Share** icon → then the **three dots** next to a user or link.
- Adjust permissions:
  - Allow or block file editing
  - Hide download option
  - Restrict resharing
  - Set expiration for time-limited access

---

## 6. Use Nextcloud Office for Collaboration

You can edit `.docx`, `.xlsx`, and `.pptx` files directly in the browser.

1. Upload or click on a supported file type.
2. It will open in **Nextcloud Office**.
3. Collaborate with colleagues in real-time.
4. Comments and suggestions are also supported.

---

## 7. Connect to Analysis Servers Using `rclone`