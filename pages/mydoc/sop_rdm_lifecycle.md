---
title: "SOP — The RDM lifecycle in the VRC"
summary: "The six-phase research data lifecycle with the concrete VRC tool, action, and data zone at each phase."
tags: [SOP, RDM, lifecycle, VRC]
last_updated: 2026-06-07
permalink: sop_rdm_lifecycle.html
sidebar: decide_sidebar
---
The lifecycle is the spine of the whole VRC. Six phases (after NFDI4Microbiota / the DECIDE site), each with the concrete VRC tool to use, the action to take, and the **data zone** you are operating in. The zone tells you which rules apply: **Green Room** (personal, no FAIR requirements) → **Shared** (group, metadata + access control) → **Published** (world, DOI + licence). Two **gates** sit between them: G1 (Green Room → Shared) and G2 (Shared → Published).

| Phase | What you do | VRC tool / action | Zone |
|---|---|---|---|
| **1. Plan** | Write the DMP, choose the metadata model, scaffold the project | RDMO (JMU) or DataPLAN → DMP into `docs/DMP/`; run `init_vrc_project.sh` to create the standard folder | Green Room |
| **2. Collect** | Acquire data, document it in real time | Instrument → `data/raw/` (lock read-only, checksum); record in **Labfolder** within 48 h; same `subject_id` everywhere | Green Room |
| **3. Process & Analyze** | Convert raw → primary → processed; run analysis | Conversion scripts in `src/` (open formats); **JupyterHub** on **HPC Julia/Bioinformatics**; code in **VRC GitLab** | **Gate G1** → Shared |
| **4. Preserve** | Store, back up, and archive long-term | cRDM **Nextcloud group folder** (nightly backup to RZ); **RZ Archive Server** for 10-year retention; open formats only | Shared |
| **5. Share / Publish** | Release data findably and citably with the right access level | **Gate G2**: DOI via WueData/Zenodo/domain repo; declare licence; controlled-access (EGA / NFDI4Health) for sensitive | **Gate G2** → Published |
| **6. Reuse** | Make it the next project's input | Persistent links + searchable metadata; published dataset becomes Phase-1 input for follow-up work (e.g. atlas / network analyses) | Published |

## Gate G1 — leaving the Green Room (Collect/Process → Shared)
Before data enters a Nextcloud group folder:
1. Metadata template applied (`data/metadata/`).
2. Pseudonymise/anonymise if patient-derived (see GDPR SOP) — **patient-identifying data does not enter the cRDM VRC**.
3. Correct group folder + access policy chosen.
4. DMP reference confirmed; raw locked read-only.

## Gate G2 — publishing (Shared → Published)
Before release:
1. Full FAIR metadata; DOI assigned (repository, not a Nextcloud link).
2. Licence declared; README complete.
3. Ethics + DPO clearance confirmed where applicable.
4. DMP updated one last time.

## Worked VRC example (microscopy PhD, CRC 1525)
Acquire on the confocal → files in HPC home (**Green Room**). Decide the session is real → fill the imaging metadata template, upload to the consortium **Nextcloud group folder**, record in Labfolder (**Gate G1 → Shared**). Convert `.czi`→OME-TIFF in `src/`, analyse on JupyterHub, version in GitLab (**Process**). Paper accepted → deposit images to IDR, code to Zenodo with a DOI, reference both (**Gate G2 → Published**).

*Related: SOP — FAIR RDM · Checklist before sharing/publishing in Nextcloud · GDPR & sensitive data SOP.*
