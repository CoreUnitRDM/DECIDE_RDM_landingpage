---
title: "Checklist — before sharing or publishing in Nextcloud (VRC)"
summary: "What to verify at each step: private folder → share a folder → push to a TEAM/group folder → share publicly → publish with a DOI."
tags: [checklist, Nextcloud, sharing, publishing, FAIR, GDPR, VRC]
last_updated: 2026-06-07
permalink: checklist_sharing_publishing.html
sidebar: decide_sidebar
---
Each step out of your private space is a deliberate act with its own checks. The steps map onto the VRC zones: **private = Green Room**, **shared/group = Shared zone (Gate G1)**, **public/DOI = Published (Gate G2)**. Work top to bottom; do not skip a tier.

> **Hard stops that apply at every tier**
> - **Patient-identifying data never enters the cRDM Nextcloud.** It stays at UKW. (GDPR SOP)
> - If data is patient-derived, it must be **pseudonymised and verified** before it leaves your private space.
> - A **Nextcloud public link is not a publication** and not a citable handle — for that you need a repository + DOI (last tier).

## Tier 0 — Private / personal folder (Green Room)
Your own Nextcloud space or HPC home. No metadata or FAIR requirements. This is where you think before you share. Nothing to check — but nothing here is backed by group access control, so don't treat it as the project's only copy.

## Tier 1 — Share a folder with specific people (internal share)
*Nextcloud → folder → Share → add internal user/group.* Use for handing a colleague a specific dataset.
- [ ] No patient-identifying data; pseudonymisation verified if applicable
- [ ] Filenames follow the convention; `subject_id` consistent
- [ ] Set the right permission level (read vs edit); add an **expiry date**
- [ ] Recipient is JMU/UKW/approved partner (not a private external account)
- [ ] You are sharing a copy of the relevant data, not your whole Green Room

## Tier 2 — Push to a TEAM / group folder (Shared zone — Gate G1)
*Nextcloud Group Folders → consortium folder with role-based ACL (request from the cRDM helpdesk).* This is the proper promotion to the Shared zone — the real Gate G1.
- [ ] **Metadata template applied** and placed in `data/metadata/`
- [ ] Pseudonymised/anonymised if patient-derived; key kept only at UKW, separate, access-logged
- [ ] Correct group folder + access policy (who in the consortium can see/edit)
- [ ] Standard folder structure present; `README.md` written
- [ ] DMP referenced; raw data locked read-only and checksummed
- [ ] Same identifiers across filename ↔ metadata ↔ Labfolder
- [ ] If sensitive: DPO-approved processing record exists before the move

## Tier 3 — Share with the public via a Nextcloud link
*Nextcloud → Share → "Share link".* Use sparingly — for a quick public hand-off, **not** as the archival/citable copy.
- [ ] Absolutely no sensitive, personal, or licence-restricted content
- [ ] A **licence** is attached (CC BY 4.0 / CC0 for data)
- [ ] Link has a **password** and an **expiry date**; permission is read-only
- [ ] Metadata + README included so the recipient can interpret it
- [ ] You understand this link can disappear — for anything to be cited, use Tier 4

## Tier 4 — Publish with a DOI (Gate G2 — the real publication)
Deposit to a repository, not a Nextcloud link.
- [ ] Repository chosen: WueData / Zenodo / domain repo (IDR, ENA, EGA, PRIDE, NFDI4Health Study Hub)
- [ ] Two-track for sensitive projects: open outputs → open repo + DOI; pseudonymised clinical → controlled-access (EGA / Study Hub) under a Data Access Agreement
- [ ] Full FAIR metadata; **DOI** assigned
- [ ] Licence declared (data + code); code mirrored to GitHub/Zenodo
- [ ] Ethics + DPO clearance covers the publication
- [ ] DMP updated one last time; README at publication is complete
- [ ] Published dataset linked from the manuscript before submission

*Related: SOP — RDM Lifecycle · SOP — FAIR RDM · GDPR & sensitive data SOP · FAIR self-check.*
