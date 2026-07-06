---
title: "Support & FAQ"
keywords: support, FAQ, Nextcloud, rclone, sync, ONLYOFFICE, versioning, team folders, ACL, FAIR
summary: "Real answers from VRC support — cloud transfers, the desktop sync client, cloud documents, large uploads, versioning, team folders, and FAIR analysis."
last_updated: 2026-07-02
permalink: faq.html
sidebar: decide_sidebar
---

A running knowledge base of issues actually hit in VRC support, each with the working answer. Compiled from the project support logs. Can't find yours? Contact the cRDM helpdesk.

## Cloud & Nextcloud

### Transfers are slow through the web interface
The browser uploader is inherently slow. Use **`rclone`** over WebDAV: set up a remote once (`rclone config` → WebDAV), then `rclone copy` up or down. Use `rclone copy` (never `rclone sync`) for raw data so nothing gets deleted. Docs: <https://rclone.org/webdav/>

### The desktop sync client uploads new files but they fail
Folder sync and download work, but a **new** file created in the synced folder fails to upload. This is a **client-side bug** in newer Nextcloud desktop clients (the NG chunking path miscalculates chunk size on fast LANs). Fixes:
- Use client **v3.5.4** or the newer stable **v3.16.6**; avoid 3.17.x and 4.x/33.x.
- Or use `rclone` (WebDAV), the Ubuntu `nextcloudcmd`, or browser drag-and-drop — none use the broken path.

### Images look blurry in a cloud document
Browser-based editors (ONLYOFFICE, Office Online) re-compress embedded images on save, and Microsoft Word compresses images by default too. To keep figures sharp:
- In Word: File → Options → Advanced → **"Do not compress images in file"**, then re-save and re-upload.
- Embed figures as **PDF** rather than PNG/JPEG — browser editors generally don't re-compress PDFs.
- For image-heavy proposals, edit locally via the sync client; the cloud copy stays in sync without recompression.

### "File size exceeds the server limit" when opening a document
The simplest fix is to **compress the images** in the .docx: Picture Format → Compress Pictures → 96 ppi, which usually drops the file well under the limit. If it persists, ask an admin — there are server-side caps that can be raised.

### Uploading very large datasets (tens of GB)
Don't drag ~100 GB through the browser — it chunks then reassembles server-side, transiently needing ~2× the space, and tabs time out. Instead:
- Use **`rclone`** (WebDAV) or the desktop sync client — both chunk **and resume**.
- For very large one-off datasets, ask an admin to place the files directly and index them.

### Recovering a deleted or overwritten document
Nextcloud keeps **versions** (each ONLYOFFICE edit or same-name re-upload makes one — restorable from the file's version history) and a **trash bin** (deleted files recoverable for 30 days via profile → "Deleted files"). Best practice: to update a document, **overwrite** it (same name → "replace") or edit in place — never delete-and-reupload, which breaks the version history. Versioning is not a substitute for backup.

### Team folders vs. sharing a folder with my group
Use **Team (Group) folders**. They're owned by the system, so they survive people leaving; they have their own quota (don't eat your space); users can't accidentally unshare or delete them; and they support **ACLs** for per-subfolder permissions. Plain shared folders are owned by one user and are fragile — use them only for small, informal collaboration.

### Restricting one subfolder inside a team folder
Use **Advanced Permissions (ACL)**: enable "Advanced Permissions" for that team folder, then on the subfolder set the ACL so the wider group is denied and only the specific users are granted access. Don't try to do this with ordinary shares.

### The password-reset link says "page not reachable"
The login and password-reset pages are restricted to the **university network**. From home, connect via the **university VPN** and try again — or ask an admin to reset the password for you.

## RDM & FAIR

### FAIR integration when I analyse my own data
*(für Selbst-Analyst:innen)*

Vieles machst du wahrscheinlich schon, ohne es "FAIR" zu nennen. **Du gibst deine Analyse nicht ab** — du bleibst Eigentümer:in und Expert:in; wir leiten nur NFDI-Guidelines auf DECIDE ab. Ziel: jede*r kann von Rohdaten → Protokoll → Notebook → Abbildung durchklicken und dein Skript nachlaufen lassen.

Dein FAIR-Workflow in Kürze:
- **Findable** — Projektordner-Template, Dateinamen `YYYYMMDD_<sample-ID>_<type>_v<N>`, konsistente sample-IDs, README + DMP.
- **Accessible** — Cloud (fürs Teilen/Backup); Code in Git.
- **Interoperable** — Metadata + kontrolliertes Vokabular (der Kern, siehe unten).
- **Reusable** — LICENSE (Daten CC-BY-4.0, Code MIT); Protokolle im ELN + Analyse in Git.

Das **"metadata model"** ist ein kontrolliertes Spaltenschema — eine Zeile pro Sample, jedes Feld aus definiertem Vokabular. Basis = das technische Single-Cell-Modell (Immendahl); du ergänzt die biologische Metadata (Organismus, Stamm, Infektionsmodell, Kondition, Zeitpunkt …). Wichtigste Felder an Ontologien binden: Gen → Ensembl/HGNC · Spezies → NCBI Taxonomy · Zelltyp → CL · Gewebe → UBERON · Krankheit → Mondo · Assay → EFO/OBI · Wirkstoff → ChEBI. Jede ID ist zugleich ein Link in andere Datenbanken — so werden deine Daten integrierbar. Übersicht: <https://ontobee.org/>.

Am Ende in ein **FAIR-Repo** (DOI = zitierbar, dauerhaft, von DFG-GWP & Journals verlangt): ArrayExpress/GEO · IDR (Imaging) · EGA (sensibel) · Zenodo/GRO.data.

---

*Compiled from real VRC support. To add an entry, contact the cRDM helpdesk. (Internal server-admin and security procedures from the support log are kept in a separate internal document, not on this public page.)*
