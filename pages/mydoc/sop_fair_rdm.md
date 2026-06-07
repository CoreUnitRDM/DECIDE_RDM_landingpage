---
title: "SOP — Making your project FAIR in the VRC"
summary: "Concrete, tool-by-tool steps to satisfy each FAIR principle using VRC Würzburg infrastructure."
tags: [SOP, FAIR, RDM, VRC]
last_updated: 2026-06-07
permalink: sop_fair_rdm.html
sidebar: decide_sidebar
---
**FAIR is the *exit standard*.** Anything that leaves your personal Green Room into a shared or published zone must be Findable, Accessible, Interoperable, and Reusable. This SOP gives the concrete VRC action for each principle — not the theory. Tick the matching items in `FAIR_self_check.md` before each gate (G1 leaving the Green Room, G2 publishing).

## Findable — concrete VRC steps
- Apply the metadata template **at upload time**, not later. Templates live in the cRDM Nextcloud share and at `github.com/CoreUnitRDM/MetaDataTemplates`; attach the filled Excel/CSV to the project's `data/metadata/` folder.
- Use **one identifier everywhere**: the same `subject_id` / `sample_id` appears in the filename (SOP file-naming), the metadata table, and the Labfolder entry.
- At publication, get a **persistent identifier (DOI)** via WueData (JMU institutional repository, `<FILL IN URL>`) or a domain repository — never rely on a Nextcloud link as the citable handle.

## Accessible — concrete VRC steps
- Store shared data in a **Nextcloud group folder** with role-based access (requested from the cRDM helpdesk), not in personal shares or public links.
- Authentication is via your **JMU/Informatikcloud identity (SSO)**; MFA is mandatory for sensitive zones.
- Keep **metadata discoverable even when data is restricted**: deposit the descriptive record openly and route the data itself through the correct controlled channel (EGA / NFDI4Health Study Hub for human-derived; UKW for patient-identifying — see the GDPR SOP).

## Interoperable — concrete VRC steps
- Convert to **open standard formats** as your *primary* data: OME-TIFF/OME-Zarr (imaging), FASTQ→BAM/CRAM/VCF (omics), CSV/Parquet over XLSX, JSON/MD over Word. Proprietary originals stay in `data/raw/` untouched.
- Use **controlled vocabularies**, not free text: MIxS/ENVO (microbiota), OME-XML/REMBI (imaging), SNOMED CT / LOINC / ICD (clinical), ChEBI/RRID (wetlab). Look up terms via the EBI OLS.
- Code missing values explicitly with standard tokens (see Metadata Template Suggestions) — never leave a cell blank.

## Reusable — concrete VRC steps
- Declare a **licence** before publishing: data → CC BY 4.0 or CC0; code → MIT / Apache-2.0 / GPL-3.0.
- Make the pipeline **reproducible**: `raw → primary → processed` must regenerate from `src/` alone, versioned in VRC GitLab (public code mirrored to `github.com/CoreUnitRDM` or Zenodo after publication).
- Ship **documentation alongside data**: README (the map), the data dictionary, and the DMP travel with the project (see the project bootstrap).

## VRC tool map at a glance
| FAIR need | VRC tool |
|---|---|
| Storage + access control | cRDM Nextcloud group folders (`coreunitrdm.biozentrum.uni-wuerzburg.de`) |
| Documentation | Labfolder ELN (via RZ), README, data dictionary |
| Metadata templates | CoreUnitRDM MetaDataTemplates + Nextcloud metadata app |
| Code / provenance | VRC GitLab (+ GitHub/Zenodo mirror at publication) |
| Compute | JupyterHub + HPC Julia I/II / HPC Bioinformatics |
| Preservation | RZ Archive Server (10-year retention) |
| Publication + DOI | WueData / Zenodo / domain repository |
| DMP | RDMO (JMU) or DataPLAN |

*Related: SOP — RDM Lifecycle · FAIR self-check · GDPR & sensitive data SOP · Metadata Template Suggestions.*
