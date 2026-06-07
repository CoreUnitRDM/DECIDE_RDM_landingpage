---
title: "SOP — GDPR & sensitive data in the VRC"
summary: "How to handle personal and patient-derived data in the VRC: legal basis, pseudonymisation, the UKW boundary, sensitive-data storage, compute, and two-track publishing."
tags: [SOP, GDPR, sensitive data, clinical, privacy, VRC]
last_updated: 2026-06-07
permalink: sop_gdpr_sensitive_data.html
sidebar: decide_sidebar
---

Sensitive data carries its constraints with it. In the VRC, **policy follows the data, not the user** — once data is personal or patient-derived, every component (Nextcloud, JupyterHub, HPC, repositories) must honour the same restrictions. This SOP is the operational guide; on any specific case the **Data Protection Officer (DPO)** and the **Ethics Committee (Ethikkommission)** have the final say. It is guidance for handling data correctly, not legal advice.

> **Three hard stops — they apply everywhere, no exceptions**
> - **Patient-identifying data never enters the cRDM VRC.** It stays inside UKW-managed infrastructure. The cRDM VRC handles only anonymised or pseudonymised subsets.
> - **If data is person-derived, it must be pseudonymised and verified *before* it leaves your private Green Room.**
> - **No identifiers in filenames, folder names, or free-text fields — ever.** Use a pseudonymised ID only.

## What counts as sensitive data

- **Personal data** — any information relating to an identifiable person (name, DOB, address, but also combinations that re-identify, e.g. rare diagnosis + location + date).
- **Special-category data (Art. 9 GDPR)** — health, genetic, and biometric data. Almost all clinical and patient-derived research data falls here and gets the strictest treatment.
- **Pseudonymised** ≠ **anonymised.** Pseudonymised data can still be re-linked via a key, so it remains personal data under GDPR. Truly anonymised data (no re-linking possible by anyone) is outside GDPR — but real anonymisation is hard; assume pseudonymised unless verified otherwise.

## Before you collect (the planning gate)

Confirm all of the following are in place — most are recorded in your DMP (legal & ethics section):

- [ ] **Legal basis** for processing identified (consent, public-interest research, etc.)
- [ ] **Ethics approval** from the Ethikkommission (JMU/UKW): `<FILL IN ref / status>`
- [ ] **Informed consent** that explicitly covers your planned use *and* reuse/publication. Data collected for study X cannot be reused for question Y without a consent that covers it.
- [ ] **DPIA** (Data Protection Impact Assessment) completed for high-risk processing
- [ ] Entry in the **VVT** (Verzeichnis von Verarbeitungstätigkeiten / record of processing activities)
- [ ] **Pseudonymisation scheme** defined: who generates the key, where it is held

## Pseudonymisation — how to do it

- The **key (ID ↔ identity map) is held only at UKW**, stored separately from the data, with **logged access**. It never travels with the dataset and never enters the cRDM VRC.
- Replace every direct and indirect identifier with a **stable pseudonymous ID** at the source. This same ID becomes the foreign key across all your metadata tables (see Metadata Templates → mixed/multimodal).
- **Verify** before any data moves: open the files and metadata and confirm no residual identifiers (including in image headers, DICOM tags, document properties, scanned free text).

## Where sensitive data lives and runs

| Activity | Open / non-personal data | Sensitive / patient-derived data |
|---|---|---|
| Storage | cRDM Nextcloud group folder | **UKW-managed zone only** — not cRDM Nextcloud |
| Compute | JupyterHub + HPC (cRDM) | **UKW perimeter compute**; only a pseudonymised subset is handed off to cRDM HPC for analysis under the federation SOP |
| Identity | JMU/Informatikcloud SSO | Same SSO, **MFA mandatory** for sensitive zones |
| Sharing | Internal share / group folder | Controlled, logged, DPO-approved processing record required first |

The handoff of a pseudonymised subset from UKW to cRDM for analysis is a **federation interface governed by SOP** — it goes one direction (UKW → cRDM for catalog + HPC), and published results return the other way. Confirm the route with your supervisor and the cRDM helpdesk before the first transfer.

## Publishing sensitive data (Gate G2 — two tracks)

Sensitive data is **not** open data. Split the outputs:

- **Open track** — processed/derived outputs that carry no re-identification risk (features, models, code, aggregate results) → open repository + DOI (Zenodo / domain repo).
- **Controlled-access track** — pseudonymised individual-level clinical/genomic data → a **controlled-access** repository (e.g. **EGA**: https://ega-archive.org/) or the **NFDI4Health Study Hub** (https://www.nfdi4health.de/), released only under a **Data Access Agreement (DAA)**.
- Register and cross-link both tracks so the paper points to everything; the **descriptive metadata stays openly discoverable even when the data is restricted**.
- Confirm **ethics + DPO clearance covers the publication** (not just the collection).

## Who to involve

- **Data Protection Officer (DPO):** `<FILL IN contact>` — authority on legal basis, DPIA, VVT.
- **Ethikkommission JMU/UKW:** `<FILL IN>` — approval and consent scope.
- **cRDM helpdesk:** for group folders, federation handoff, controlled-access deposits.
- **Your supervisor / data steward:** named in the DMP.

## GDPR checks mapped to the gates

**Gate G1 (leaving the Green Room → Shared):** pseudonymisation done and verified · DPO-approved processing record exists · key held separately at UKW · correct access policy chosen · no identifiers in names/metadata.

**Gate G2 (Shared → Published):** two-track split decided · controlled-access repository + DAA for individual-level data · ethics/consent covers publication · descriptive metadata deposited openly.

*Related: SOP — RDM Lifecycle · SOP — Making your project FAIR · FAIR self-check · Checklist before sharing/publishing in Nextcloud · DMP Template (legal & ethics section).*
