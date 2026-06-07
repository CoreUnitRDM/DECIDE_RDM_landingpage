---
title: "FAIR self-check"
summary: "A quick tick-box self-assessment to run before each gate — G1 (leaving the Green Room) and G2 (publishing). Companion to SOP — Making your project FAIR."
tags: [checklist, FAIR, self-check, VRC]
last_updated: 2026-06-07
permalink: fair_self_check.html
sidebar: decide_sidebar
---

Run this before each gate. It is the tick-list companion to the *Making your project FAIR* SOP — if an item fails, go back to that SOP for the concrete VRC step. **FAIR is the exit standard**: you only owe these once data leaves your personal Green Room.

## Findable
- [ ] Metadata template filled **at upload time** and saved in `data/metadata/`
- [ ] **One identifier everywhere** — the same `subject_id` / `sample_id` in filename, metadata, and Labfolder
- [ ] Filenames follow the naming convention (no spaces, dates as `YYYYMMDD`)
- [ ] (At publication) a **persistent identifier / DOI** is assigned via WueData or a domain repository — not a Nextcloud link

## Accessible
- [ ] Shared data sits in a **Nextcloud group folder** with role-based access, not a personal or public link
- [ ] Access is via **JMU/Informatikcloud SSO**; **MFA enabled** for sensitive zones
- [ ] For restricted data: the **descriptive metadata is still openly discoverable**, and the data itself is routed through the correct controlled channel (EGA / NFDI4Health Study Hub; UKW for patient-identifying)

## Interoperable
- [ ] Data is in **open standard formats** (OME-TIFF/Zarr, BAM/CRAM/VCF, CSV/Parquet, JSON/MD) — proprietary originals stay untouched in `data/raw/`
- [ ] Categorical fields use **controlled vocabularies / ontologies**, not free text (MIxS, OME/REMBI, SNOMED CT/LOINC, ChEBI/RRID — look up via EBI OLS)
- [ ] Missing values use **standard tokens**, never blank cells

## Reusable
- [ ] A **licence** is declared — data: CC BY 4.0 / CC0; code: MIT / Apache-2.0 / GPL-3.0
- [ ] The pipeline is **reproducible**: `raw → primary → processed` regenerates from `src/` alone, versioned in VRC GitLab
- [ ] **Documentation travels with the data**: README (the map), data dictionary, and DMP

## Gate quick-check

**Gate G1 — leaving the Green Room:** Findable + Interoperable items pass · metadata applied · pseudonymised if person-derived · access policy chosen.

**Gate G2 — publishing:** all four sections pass · DOI assigned · licence declared · ethics/DPO clearance where applicable · README complete.

*Related: SOP — Making your project FAIR · SOP — RDM Lifecycle · Checklist before sharing/publishing in Nextcloud · SOP — GDPR & sensitive data.*
