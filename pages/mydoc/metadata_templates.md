---
title: "Metadata Template Suggestions — VRC Würzburg"
summary: "The core multi-table metadata model, per-domain field/standard suggestions, the missing-value tokens, and where to get the templates."
tags: [metadata, template, FAIR, VRC]
last_updated: 2026-06-07
permalink: metadata_templates.html
sidebar: decide_sidebar
---
Decide the metadata model **before** you collect. Templates live in the cRDM Nextcloud share and at `github.com/CoreUnitRDM/MetaDataTemplates`; a Nextcloud metadata app / generator is in development. Attach the filled template to `data/metadata/` and keep a `data_dictionary.md` defining every column.

## The core model (all domains)
Use a **normalised, multi-table** structure rather than one wide sheet:
1. **Subject / sample table** — one row per individual or sample; biological metadata.
2. **Experiment / acquisition table** — one row per recording; technical metadata + file path.
3. **Link table** — connects subjects to experiments (many-to-many, foreign keys).

**Rules (non-negotiable):**
- One row = one entity. No merged cells, no multi-value cells.
- Machine-readable headers with units: `subject_id`, `shear_rate_s`, `n_frames` — no spaces.
- Controlled vocabularies (ontologies) for categorical fields; enforce with Excel dropdown validation.
- Never leave a blank to mean "not done" — use an explicit token (below).
- Ship a data dictionary: every column, its unit, allowed values.

## Missing-value tokens (use instead of blanks)
After the INSDC / DataCite / NFDI4Microbiota conventions:

| Situation | Token |
|---|---|
| Field doesn't apply to this sample | `not applicable` |
| Value exists but can't be obtained | `not available` |
| Measurement was never taken | `not collected` |
| Value withheld for now (embargo) | `not provided` |
| Value exists but is confidential (privacy/legal) | `restricted access` |

## Per-domain suggestions
**Microscopy / bioimaging**
- Standard: OME-XML / OME-NGFF; REMBI for reporting; FBbi ontology
- Key fields: instrument, objective, `pixel_size_um`, channels + fluorophores, `n_frames`, time-step, sample, condition
- Populate from Bio-Formats on conversion; supplement channel/condition mapping by hand
- Community: NFDI4BIOIMAGE · repos: IDR, BioImage Archive
- Gotcha: channel order and pixel-size units are the #1 source of wrong analyses — capture explicitly.

**Omics (genomics / transcriptomics / proteomics / metabolomics)**
- Standard: MIxS (+ MIMS/MIGS/MIMARKS), GA4GH Phenopackets, MIAPE (proteomics)
- Key fields: library prep, platform, read length, reference genome, sample sheet linking sample↔file
- Templates: CoreUnitRDM MetaDataTemplates; ENA submission checklists
- Repos: ENA/SRA (open), EGA (controlled human), MetaboLights, PRIDE
- Gotcha: sample-sheet errors propagate through the whole pipeline — validate before running.

**Clinical research**
- Standard: FHIR / CDISC; vocabularies SNOMED CT, LOINC, ICD-10/11; OMOP common data model
- Key fields: **pseudonymised ID only**, visit, instrument/assay, consent reference
- Tools: REDCap; study metadata via NFDI4Health Study Hub
- Gotcha: consent scope — data collected for study X cannot be reused for question Y without consent extension. No identifiers in any free-text field.

**Wetlab / molecular biology**
- Standard: RRID (reagents/antibodies), Cellosaurus (cell lines + STR), ChEBI (chemicals)
- Key fields: reagent lot/batch, antibody catalogue + RRID, cell passage, protocol DOI (protocols.io)
- Repos: Zenodo for assays + code
- Gotcha: lot numbers and passage live in metadata, not in your head.

**Mixed / multimodal (clinical + imaging + omics)**
- One **master pseudonymised ID** is the foreign key across all tables.
- Treat the whole project at the sensitivity of its strictest layer.

*Related: SOP — FAIR RDM · DMP Template · Checklist before sharing/publishing in Nextcloud.*
