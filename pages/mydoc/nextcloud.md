---
title: "Using Nextcloud for Research Data Management"
keywords: Research Data Management, RDM, Cloud, Version control, Backup, Activity Log, Storage, Exchange, Rclone
last_updated: July 10, 2025
tags: [nextcloud, data management, cloud storage, würzburg university, rclone]
summary: Practical guide for using Nextcloud for secure data storage, sharing, collaboration, and integration with research workflows.
sidebar: decide_sidebar
permalink: nextcloud.html
folder: mydoc
---

Nextcloud is a secure cloud platform for managing and sharing research data at Würzburg University. This guide provides **step-by-step instructions** to register, sync and share data, collaborate using Office tools, and connect your data to analysis servers using `rclone`.

---

## 1. Registration and Login

### A. Register and Log In

- Visit: [coreunitrdm.biozentrum.uni-wuerzburg.de](https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/)
- Register for an account and wait for approval.
- Log in using your assigned username and password.

---

## 2. Upload and Download Files

### A. Upload via Browser

1. Log in to the web interface.
2. Click the **“+”** icon → **Upload File** or **Upload Folder**.
3. Or drag-and-drop files directly into your folder structure.

### B. Download Files

1. Right-click on any file or folder.
2. Select **Download** to retrieve a ZIP archive or the individual file.

---

## 3. Synchronize with the Desktop or Mobile Client

### A. Install the Nextcloud Client

- Download from the [Nextcloud Client Page](https://nextcloud.com/install/#install-clients)  
  *(Windows, macOS, Linux, iOS, and Android supported)*

### B. Set Up Synchronization

1. Launch the client after installation.
2. Server address: `https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/`
3. Enter your username and password.
4. Choose folders to sync locally.

> 💡 **Tip**: Use **selective sync** to save space when handling large datasets.

---

## 4. Share Data Securely

### A. Public Link Sharing

1. Click the **Share** icon beside a file or folder.
2. Create a public link.
3. Configure access:
   - Password protection
   - Expiration date
   - Download or upload permissions

### B. Share with Specific Users

1. Enter the user’s name or email.
2. Set specific access levels: view, edit, upload, or delete.

🔗 [Official File Sharing Guide](https://docs.nextcloud.com/server/latest/user_manual/en/files/sharing.html)

---

## 5. Customize File Access Rights

- Click the **Share** icon → then the **three-dot menu (⋮)** next to a user or link.
- Adjust:
  - Edit or view-only access
  - Download visibility
  - Resharing rights
  - Expiration date

🔗 [Advanced Access Rights (ACLs)](https://nextcloud.com/blog/access-control-lists/)

---

## 6. Use OnlyOffice in Nextcloud

You can edit Microsoft Office files directly in the browser:

1. Click on any `.docx`, `.xlsx`, or `.pptx` file.
2. It opens in **OnlyOffice**.
3. Collaborate live with colleagues.
4. Add comments and track changes.

---

## 7. Restore Deleted Files or Previous Versions

### A. Restore Deleted Files

- Open the **Deleted Files** tab in the left sidebar.
- Click **Restore** to recover a file or folder.

### B. Restore Previous Versions

- Hover over a file → click the **three-dot menu (⋮)** → choose **Versions**.
- Select and restore the desired version.

---

## 8. Connect to Analysis Servers Using `rclone`

You can mount or transfer data from Nextcloud directly to an HPC or remote server using `rclone` + WebDAV.

🔗 [rclone WebDAV Documentation](https://rclone.org/webdav/)

### A. Install `rclone`

```bash
sudo apt install rclone
```

### B. Configure a New Remote

```bash
rclone config
```

- Choose `n` for new remote
- Name it: `nextcloud`
- Type: `webdav`
- URL: `https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/remote.php/dav/files/YOURUSERNAME/`
- WebDAV type: `Nextcloud`
- Enter your username and an **App Password** (generate it in *Settings → Security → App Passwords*)

### C. Use `rclone` to Mount or Copy Files

**Mount your Nextcloud folder:**

```bash
rclone mount nextcloud:/ ~/mnt/nextcloud --vfs-cache-mode writes
```

**Copy files to/from Nextcloud:**

```bash
rclone copy /local/folder nextcloud:/your-folder --progress
```

> 🔐 App passwords are safer than your login credentials and can be revoked at any time.

---

## 9. Need Help?

**Johannes Balkenhol**  
Chair of Bioinformatics, University of Würzburg  
✉️ [johannes.balkenhol@uni-wuerzburg.de](mailto:johannes.balkenhol@uni-wuerzburg.de)  
🌐 [https://www.biozentrum.uni-wuerzburg.de/bioinfo/](https://www.biozentrum.uni-wuerzburg.de/bioinfo/)

---

{% include links.html %}
