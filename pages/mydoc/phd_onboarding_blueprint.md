---
title: "RDM Onboarding Blueprint for PhD Projects"
summary: "A day-one, FAIR-by-default workflow for every new PhD project in the VRC, anchored to the data zones, gates, and component catalog."
tags: [SOP, onboarding, PhD, RDM, FAIR, VRC]
last_updated: 2026-06-07
permalink: phd_onboarding_blueprint.html
sidebar: decide_sidebar
---

**A day-one, FAIR-by-default workflow for every new PhD project in the VRC**
Version 1.0 · domain-agnostic blueprint · adapt the `<FILL IN>` and *domain* placeholders per project before sharing.

> **What this is.** A generalized version of the cRDM onboarding SOP, written to serve *any* PhD project across the VRC consortia (basic, clinical, and mixed). It keeps the same practical procedures but (a) makes domain-specific choices pluggable instead of hard-coded, and (b) anchors every step to the VRC architecture — the data zones, the gates, the five principles, and the component catalog. It operationalizes the Architecture Vision for a single researcher's first weeks.

---

## 0. How to use this blueprint

These are **Standard Operating Procedures (SOPs)** — the minimum practices every VRC member follows from day one, *before* any data is collected. The goal: **make every project reproducible and FAIR by default, not as an afterthought.**

The single most expensive mistake in research data is fixing structure *after* the data exists. Almost every recurring problem — IDs that don't match between files and tables, missing annotations, processed files no one can trace back to raw — comes from skipping the setup steps below. Twenty minutes of setup on day one saves weeks later.

Read SOPs 1–3 before you touch any data. Apply the rest as the project reaches each stage.

### The VRC frame (read once, then it stays in the background)

Everything below sits inside the VRC's structure. Three ideas are enough to orient you:

- **Three data zones.** Your work moves through a **Green Room** (your personal, unstructured workspace — no FAIR rules apply, throw data in freely), a **shared / curated zone** (team and project data, with metadata, access control, and a DMP), and a **published zone** (public, with a DOI and a license). You decide *deliberately* when to move data forward — it never drifts across by accident.
- **Two gates.** Moving between zones passes a gate. **Gate G1** (leaving the Green Room): metadata applied, anonymisation done if the data is person-derived, access policy chosen. **Gate G2** (publishing): full FAIR metadata, DOI, license, repository, and ethics/DPO clearance where applicable. The SOPs below are mostly about being ready to pass these gates without pain.
- **FAIR is the exit standard.** Anything that leaves your Green Room must be Findable, Accessible, Interoperable, Reusable. Inside the Green Room you owe nothing; the moment you share, you do.

> **The three pillars.** Every project rests on three things that must stay linked: **Data** (the files → Nextcloud), **Documentation** (what they mean and how they were made → LabFolder ELN + metadata + README), and **Analysis** (the code that turns data into results → GitLab/Git + JupyterHub/HPC). A result you cannot trace back through analysis → documentation → data is not reproducible. SOP 8 keeps these three connected — and it is the same linking the VRC enforces between components.

---

## SOP 1 — Project folder structure

Create the same skeleton for every project, whatever the discipline. A consistent structure means anyone — including future-you and the next PhD student — can open any project and immediately know where things are.

```
project-name/
├── README.md              <- project overview, the map to everything (see SOP 8)
├── LICENSE                <- how others may use code/data
├── .gitignore             <- tells git what NOT to track (data, secrets, large files)
├── environment.yml        <- computational environment, exact package versions
├── data/
│   ├── raw/               <- ORIGINAL, IMMUTABLE data. Never edit. Read-only. (this is your Green Room intake)
│   ├── primary/           <- raw converted to clean, open, analysis-ready format
│   ├── processed/         <- derived data (features, tables) produced by code
│   └── metadata/          <- metadata tables, templates, data dictionary
├── notebooks/             <- analysis notebooks, numbered: 01_, 02_, ...
├── src/                   <- reusable code (the pipeline that makes data/ from data/raw)
├── results/
│   ├── figures/
│   └── tables/
├── docs/                  <- protocols, SOPs, DMP, reports, manuscript
└── project_management/    <- meeting notes, planning
```

**Rules**

- `data/raw/` is **read-only**. Set it that way: `chmod -R a-w data/raw/`. Raw data is the ground truth; if it changes, nothing downstream is trustworthy.
- Code lives in `src/` and `notebooks/`; **data does not live in git** (see SOP 4) — it lives in Nextcloud (SOP 5).
- The structure is the same whether the project is 3 files or 30,000, and whether the data is images, sequences, spreadsheets, or instrument logs. Don't invent a new layout per project.

This skeleton follows The Turing Way's reproducible-project template — clone it instead of building by hand:
- Template repo: https://github.com/the-turing-way/reproducible-project-template
- Cookiecutter Data Science (alternative, Python-oriented): https://cookiecutter-data-science.drivendata.org/

---

## SOP 2 — File and folder naming

A filename should tell you what's inside **without opening it**, and should sort correctly on its own.

**The rules (non-negotiable, every discipline):**

1. **No spaces.** Use underscores `_` to separate fields and hyphens `-` within a field. Spaces break command-line tools and scripts.
2. **No special characters** (`/ \ : * ? " < > | & $ # % ! @`). They are interpreted differently across operating systems.
3. **Dates as `YYYYMMDD`** (or `YYYY-MM-DD`). The only format that sorts chronologically by default.
4. **Leading zeros** for sequences: `01, 02, ... 10` and `001 ... 100`, so files stay in order.
5. **Most general field first, most specific last** — so related files group together.
6. **Be consistent.** Pick the convention once, write it down in the README, everyone uses it.

**Pattern:**
```
YYYYMMDD_project_subject_condition_type_vNN.ext
```

**Examples — same pattern, different fields per domain:**
```
# imaging          20260607_<project>_<sampleID>_<condition>_<modality>_v01.tif
# sequencing       20260607_<project>_<sampleID>_<assay>_<readtype>_v01.fastq.gz
# tabular/clinical 20260607_<project>_<cohort>_<timepoint>_measurements_v01.csv
# notebooks        01_data-cleaning.ipynb   02_feature-extraction.ipynb
```

The *fields* are domain-specific; the *pattern and rules* are universal. Notebook naming (Turing Way convention): `NN_short-description` — the number orders execution, the description says what it does.

References:
- Harvard Biomedical Data Management — file naming: https://datamanagement.hms.harvard.edu/collect/file-naming-conventions
- Stanford Libraries — naming case studies: https://guides.library.stanford.edu/data-best-practices
- Caltech file-naming worksheet (fill-in template): https://authors.library.caltech.edu/103626/

---

## SOP 3 — Raw → primary → processed (the data lifecycle, in your Green Room)

Data moves through stages. Each stage has a fixed rule about what you may do to it. This is the per-file version of the VRC zone model: raw is your Green Room intake; the pipeline that follows is what makes the data ready to pass **Gate G1**.

| Stage | What it is | Editable? | Made by | Example (replace per domain) |
|---|---|---|---|---|
| **raw** | Exactly what came off the instrument / from the source | **NEVER edit. Read-only.** | Instrument / source | proprietary instrument files, original source export |
| **primary** | Raw converted to an open, standard, clean format — same information, no analysis yet | Generated by code only | Conversion script in `src/` | open standard format, normalised metadata tables |
| **processed** | Derived data: features, embeddings, model outputs | Generated by code only | Analysis code | feature tables, coordinates, model files |
| **results** | Figures, tables, final numbers | Generated by code only | Analysis code | figures, summary tables |

**Which files are "stable"?**

- **Raw is immutable** — back it up in ≥2 places (SOP 5) and never touch it again.
- **Open standard formats are stable for the long term.** Prefer open over proprietary: `.csv`/`.tsv`/`.parquet` over `.xlsx`; open archival formats over instrument-native ones (e.g. OME-TIFF/OME-Zarr for imaging, standard sequence formats for genomics); `.txt`/`.md`/`.json` over Word. Proprietary formats can become unreadable in 10 years. Find the right open format for your field via FAIRsharing (SOP 7).
- **Everything downstream of raw must be reproducible by re-running code.** If you deleted `data/primary/` and `data/processed/`, you should be able to regenerate them from `src/`. If you can't, the pipeline is broken.

**The golden rule:** raw → primary → processed is a **one-way pipeline written in code**. No manual edits in the middle. A manual edit you can't reproduce is a silent error waiting to happen.

Reference — The Turing Way RDM chapter: https://book.the-turing-way.org/reproducible-research/rdm/

---

## SOP 4 — Version control with Git (VRC GitLab / GitHub)

Git tracks **code and documentation**, not data. Use it from commit one. The VRC provides GitLab as a component; open consortia (like DECIDE) also use GitHub. The commands are identical — point `origin` at whichever your project uses.

**Setup (once):**
```bash
git config --global user.name "Your Name"
git config --global user.email "you@institution.de"
```

**Per project:**
```bash
cd project-name
git init
# create .gitignore FIRST (see below), then:
git add .
git commit -m "Initial project structure"
git remote add origin git@<FILL IN: gitlab.your-vrc.de or github.com>/<org>/project-name.git
git push -u origin main
```

**`.gitignore` — keep data and secrets OUT of git** (extend the data patterns for your domain's file types):
```gitignore
# Data — never commit (lives in Nextcloud, SOP 5)
data/raw/
data/primary/
data/processed/
*.<your raw extension>     # e.g. *.lif *.czi *.fastq.gz *.bam *.h5

# Large / generated
results/
*.ckpt
*.pth

# Environments & secrets
__pycache__/
.ipynb_checkpoints/
.env
*.key
```

**Daily habits:**
- Commit small and often, with messages that say *why*: `git commit -m "Fix ID-matching bug in converter"`.
- Push at the end of every working day.
- One repo per project. **Never commit data, passwords, or person-identifying information.**

**Why not data in git?** Git is built for text/code; large binary data bloats the repo permanently and can't be diffed. Data goes to Nextcloud (SOP 5); for *versioned* data, see **DataLad** (git for data): https://www.datalad.org/

Learn git: https://swcarpentry.github.io/git-novice/ · GitHub docs: https://docs.github.com/get-started

---

## SOP 5 — Storage & backup with Nextcloud

Nextcloud is the VRC component where **data** lives and gets backed up (git is for code). This is your shared / curated zone storage.

**The 3-2-1 backup rule:** 3 copies of important data, on 2 different media, 1 off-site. Raw data especially.

**Layout on Nextcloud** mirrors the project structure:
```
<FILL IN: VRC Nextcloud server>/Projects/project-name/
├── data/raw/
├── data/primary/
├── figures/
└── documents/
```

**Sync from HPC / workstation with `rclone`** (scriptable, reliable for large datasets):
```bash
# one-time: rclone config  -> set up a "nextcloud" remote (WebDAV)
# then sync raw data up (copy, never sync-delete raw):
rclone copy ~/Projects/project-name/data/raw/ \
  "nextcloud:Projects/project-name/data/raw/" -v --no-update-modtime

# pull figures back down:
rclone copy "nextcloud:Projects/project-name/figures/" \
  ~/Projects/project-name/results/figures/ -v
```

- Use `rclone copy` (adds files) for raw data — **never** `rclone sync` on raw (sync can delete).
- For very large transfers, ask the VRC helpdesk about FEX large-file transfer.
- Rclone docs: https://rclone.org/webdav/ · Nextcloud docs: https://docs.nextcloud.com/

> **Sensitive / person-derived data branch.** If your raw data is patient- or person-derived, it does **not** go to the open cRDM Nextcloud. It stays in the UKW-managed zone, and only an anonymised/pseudonymised subset is handed off for analysis under the federation SOPs. Confirm the route with your supervisor and the VRC helpdesk *before* first upload — this is a Gate G1 decision, not an afterthought.

---

## SOP 6 — Electronic lab notebook (LabFolder)

LabFolder is the VRC component where **documentation** lives: what you did, when, why, and what happened. It connects a physical or computational experiment to its data files.

**Record in real time, not from memory:**
- Date, operator, sample/subject ID (the **same ID** used in filenames and metadata — SOP 7).
- Protocol used and **any deviation** from it (the equivalent of "used setting B instead of A", "replicate 3 not collected").
- The exact **filename(s)** produced, so the notebook entry points to the data.
- Anomalies (instrument drift, interruptions, contamination, failed runs) — these explain outliers later.
- Submit the entry within 48 h while details are fresh.

**The link rule:** every ELN entry names the data file it produced; every data file's metadata names the ELN entry / subject ID. This is half of SOP 8 and a precedent for the VRC's cross-component click-through (Nextcloud dataset → LabFolder protocol → GitLab script).

LabFolder: https://www.labfolder.com/ · Comparing ELNs: https://elnfinder.org/ · Harvard ELN guidance: https://datamanagement.hms.harvard.edu/

---

## SOP 7 — Metadata models (pick your domain's standard)

Metadata is data about your data: it makes files findable and interpretable. Decide the model **before** collecting, and use controlled vocabularies so values are consistent and machine-readable. This mirrors the VRC's four metadata layers (core → domain → project → provenance).

**Use a normalised, multi-table model** (don't cram everything into one messy sheet). A proven pattern:

1. **Subject / sample table** — one row per individual or sample; descriptive metadata.
2. **Experiment / acquisition table** — one row per recording/run; technical metadata (instrument, parameters, file path).
3. **Link table** — connects subjects to experiments (a many-to-many bridge with foreign keys).

**Rules:**
- **One row = one entity.** No merged cells, no multi-value cells.
- **Column headers are machine-readable**: `subject_id`, `value_unit`, `n_replicates` — no spaces, units in the name.
- **Use controlled vocabularies / ontologies**, not free text, for categorical fields. **Pick the standard for your domain** rather than inventing one (this is the VRC §6.2 principle — use existing standards, contribute back if inadequate):
  - Clinical conditions → **SNOMED CT** (https://www.snomed.org/) · Lab values → **LOINC** (https://loinc.org/)
  - Chemicals/interventions → **ChEBI** (https://www.ebi.ac.uk/chebi/)
  - Bioimaging → **OME** / **FBbi** (NFDI4BioImage alignment)
  - Genomics / human-derived → **GA4GH**, **EGA** conventions, **NFDI4Health**
  - Microbiology → **NFDI4Microbiota** schemas
  - Generic experimental → **EDAM** ontology, **RDA** working-group conventions
  - **Don't know your field's standard? → FAIRsharing: https://fairsharing.org/**
- **Enforce values with dropdowns** in the template (spreadsheet data validation) so typos can't enter.
- **Never leave a field blank to mean "not done."** Write it explicitly (`not_acquired`) — blank is ambiguous.
- **Include a data dictionary**: a sheet/file defining every column, its unit, and allowed values.

Every dataset that passes Gate G1 also needs the VRC **core metadata** (identifier, title, creator, date, project, license), captured via the metadata template in the knowledgebase. For querying across many experiments, generate a **SQLite database** from the tables.

Metadata standards background — The Turing Way: https://book.the-turing-way.org/reproducible-research/rdm/rdm-metadata

---

## SOP 8 — Linking the three pillars

A result is only reproducible if you can walk backwards: **figure → code that made it → data it used → documentation of how that data was created.** Build these links deliberately — this is the single-project version of the VRC's cross-component integration.

**The README is the map** (`README.md` at the project root). It should answer, for a newcomer:
- What is this project and who owns it?
- Where is the data (raw on Nextcloud at `<path>`, primary generated by `src/convert.py`)?
- How do I set up the environment (`conda env create -f environment.yml`)?
- How do I reproduce the results (run notebooks `01` → `0N` in order)?
- Where is the metadata and the data dictionary?

**The linking chain in practice:**
- Filenames, metadata `subject_id`, and ELN entries all use the **same identifiers**.
- Each notebook/script states its **input path and output path** explicitly.
- Each figure's filename or caption references the script and data version that produced it.
- A `data/metadata/` table maps every raw file → its subject → its processed outputs.

README templates / generators:
- The Turing Way README guidance: https://book.the-turing-way.org/communication/aesthetics/aesthetics-readme
- README generator for replication packages: https://www.templatereadme.org/

---

## SOP 9 — Compute: JupyterHub, HPC, and cloud

**Reproducible environments first.** Never `pip install` randomly. Pin everything:
```bash
conda env create -f environment.yml      # create from spec
conda env export > environment.yml       # save exact versions before sharing/publishing
```

**JupyterHub on HPC** (the VRC analysis component) — log in through `<FILL IN: VRC JupyterHub URL>`, work in `notebooks/`, select your project's conda kernel. It reads data from Nextcloud without copying it out of the managed zone. Use it for exploration and small-to-medium jobs.

**HPC batch** (heavy compute) — for large jobs, training, big conversions. Submit through the scheduler (SLURM):
```bash
sbatch run_pipeline.sh        # submit a batch job
squeue -u $USER               # check your jobs
```
Keep working data on the HPC's fast scratch storage; **sync results and back up raw to Nextcloud** (SOP 5) — scratch is not backed up and is periodically wiped.

**HPC ↔ cloud pattern:** raw data and backups live in Nextcloud; active compute happens on HPC scratch; finished outputs sync back. Document the exact paths in the README so the flow is reproducible. For sensitive data, compute stays inside the UKW perimeter — see the SOP 5 branch.

Carpentries HPC intro: https://carpentries-incubator.github.io/hpc-intro/ · Reproducible environments (Turing Way): https://book.the-turing-way.org/reproducible-research/renv

---

## SOP 10 — Data Management Plan (DMP)

Write the DMP at the **start** of the project (funders — DFG, BMBF, EU Horizon — increasingly require it). It records how data will be created, stored, documented, shared, and preserved — most answers come straight from these SOPs.

**Tool:** **RDMO** (Research Data Management Organiser), the German standard, operated as the **DMP4NFDI** base service:
- RDMO project: https://rdmorganiser.github.io/en/
- VRC / institutional RDMO instance: `<FILL IN>`
- Alternative: DMPonline (DCC): https://dmponline.dcc.ac.uk/

A DMP covers: project info, data collection & formats, documentation & metadata, storage & backup, legal/ethics (especially for person-derived data — note DPO/DPIA/VVT requirements where relevant), and sharing/preservation. Update it when things change — it's a living document, referenced at Gate G1.

DMP guidance — Turing Way: https://book.the-turing-way.org/project-design/dmp

---

## SOP 11 — Publishing data (Gate G2)

When results are published, the underlying data should be findable and citable (a DOI), with the right access level. This is Gate G2: full FAIR metadata, DOI, license, repository, and ethics/DPO clearance where applicable.

**Choose a repository** (don't just default to one):
- VRC route: **WueData** (institutional) + the **RZ archive** for 10-year retention.
- Find a domain repository: **re3data** (https://www.re3data.org/), **FAIRsharing** (https://fairsharing.org/), or DataCite's **Repository Finder** (https://repositoryfinder.datacite.org/).
- **Domain-specific beats generalist** — richer metadata, your community finds it (e.g. **BioImage Archive / IDR** for imaging; sequence archives for genomics).
- **Generalist fallback:** **Zenodo** (https://zenodo.org/) — gives a DOI, integrates with Git, takes code + data.

**Sensitive / person-derived data ≠ open data.** Use a **two-track** approach (the cRDM ↔ UKW federation in practice):
- Open outputs (processed data, features, models, code) → open repository (Zenodo / domain archive) + DOI.
- Pseudonymised clinical/personal data → **controlled-access** repository (e.g. **EGA**: https://ega-archive.org/), released only under data-access agreements; in the German health context, register via **NFDI4Health Study Hub** (https://www.nfdi4health.de/).
- Register and link both tracks so the published paper points to everything.

**Before publishing:** run the **cRDM FAIR checklist**, confirm against the FAIR principles (https://www.go-fair.org/fair-principles/), and confirm a license is attached (data: CC-BY 4.0 or CC0; code: MIT/Apache/GPL). License chooser: https://choosealicense.com/

---

## Domain adaptation — instantiating this blueprint

This blueprint is deliberately domain-neutral. To turn it into *your* project's working SOP, fill in four things and the rest follows:

| Slot | Where it's used | How to choose |
|---|---|---|
| **Raw file format(s)** | SOP 2 naming, SOP 3 stages, SOP 4 `.gitignore` | What your instrument/source produces |
| **Open archival format** | SOP 3 primary stage | The open standard for your field (via FAIRsharing) |
| **Controlled vocabularies / ontology** | SOP 7 metadata | Your domain's standard (SNOMED, OME, GA4GH, NFDI4Microbiota, EDAM…) |
| **Repository** | SOP 11 publishing | Domain repository via re3data; Zenodo as fallback |
| **Data sensitivity** | SOP 5, SOP 9, SOP 11 | Open → cRDM VRC; person-derived → UKW route + controlled access |

Everything else — folder skeleton, naming rules, raw-is-immutable, git-for-code, ELN-in-48h, the README map, the DMP, the two gates — is identical for every PhD project.

---

## Mapping to the VRC research data lifecycle

| VRC lifecycle phase | Blueprint SOP(s) | Zone / gate |
|---|---|---|
| 1. Plan | SOP 10 (DMP), SOP 1 (structure) | — |
| 2. Acquire | SOP 2 (naming), SOP 3 (raw), SOP 6 (ELN) | Green Room |
| 3. Process | SOP 3 (primary/processed), SOP 7 (metadata) | Green Room → **Gate G1** → shared |
| 4. Analyse | SOP 4 (git), SOP 9 (compute), SOP 8 (links) | shared / curated |
| 5. Preserve | SOP 5 (backup), RZ archive | shared / curated |
| 6. Publish | SOP 11 | shared → **Gate G2** → published |
| 7. Reuse | published datasets become the next student's findable input | published |

---

## Quick-start checklist

**Day 1**
- [ ] Get VRC accounts: GitLab/GitHub org, Nextcloud, LabFolder, JupyterHub/HPC `<FILL IN>`
- [ ] Confirm your **data sensitivity** route (open cRDM vs. UKW) with supervisor + helpdesk
- [ ] Clone the project template (SOP 1); create the folder skeleton
- [ ] Read SOPs 1–3

**Week 1**
- [ ] `git init` + first commit + push; add `.gitignore` (SOP 4)
- [ ] Set `data/raw/` read-only; set up Nextcloud + rclone backup (SOP 5)
- [ ] Pick your domain's controlled vocabularies; write the metadata template + data dictionary (SOP 7)
- [ ] Start the DMP in RDMO (SOP 10)
- [ ] Write the first README (SOP 8)

**Ongoing**
- [ ] Record every experiment in the ELN within 48 h (SOP 6)
- [ ] Commit code daily; keep raw → primary → processed as a code-only pipeline (SOP 3)
- [ ] Keep the same IDs across filenames, metadata, and ELN (SOP 8)
- [ ] Treat Gate G1 and Gate G2 as deliberate steps, not paperwork

---

## Knowledgebase — resources by category

**Reference handbook (read this first)**
- The Turing Way — reproducible, ethical, collaborative data science: https://book.the-turing-way.org/

**FAIR & RDM portals**
- GO FAIR — FAIR principles: https://www.go-fair.org/fair-principles/
- Forschungsdaten.info (German RDM portal): https://www.forschungsdaten.info/en/
- OpenAIRE RDM guide: https://www.openaire.eu/how-to-comply-with-h2020-mandates-for-data-management-plans

**NFDI (German national research data infrastructure)**
- NFDI4Microbiota knowledge base: https://knowledgebase.nfdi4microbiota.de/
- NFDI4Health (health data): https://www.nfdi4health.de/
- NFDI4BioImage (microscopy/imaging) training: https://nfdi4bioimage.github.io/training/readme.html
- Metadata standards catalog: https://github.com/NFDI4Microbiota/MetadataStandards
- Find your consortium: https://www.nfdi.de/

**Project structure & naming**
- Reproducible project template: https://github.com/the-turing-way/reproducible-project-template
- Cookiecutter Data Science: https://cookiecutter-data-science.drivendata.org/
- File-naming worksheet (Caltech): https://authors.library.caltech.edu/103626/

**DMP tools**
- RDMO / DMP4NFDI: https://rdmorganiser.github.io/en/
- DMPonline: https://dmponline.dcc.ac.uk/

**Repositories & publishing**
- re3data (registry): https://www.re3data.org/ · FAIRsharing: https://fairsharing.org/ · Repository Finder: https://repositoryfinder.datacite.org/
- Zenodo (generalist + DOI): https://zenodo.org/ · EGA (controlled-access clinical): https://ega-archive.org/

**Skills training**
- Git: https://swcarpentry.github.io/git-novice/ · HPC intro: https://carpentries-incubator.github.io/hpc-intro/ · DataLad: https://www.datalad.org/

---

*Living document. When a procedure changes, update the SOP and note the version. Replace all `<FILL IN>` and *domain* placeholders with your project's specifics before sharing with students. Companion documents: VRC Architecture Vision (the strategic frame), cRDM FAIR Checklist (Gate G2), cRDM Service Lifecycle SOP, cRDM Mail-Access SOP.*
