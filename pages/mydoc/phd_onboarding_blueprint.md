---
title: "How to start a project"
keywords: RDM, FAIR, workflow, project start, onboarding, data lifecycle, DMP
summary: "One workflow, ordered along the research data lifecycle. Start with a data management plan and follow the steps — each links to the tool and the detailed how-to you need."
last_updated: 2026-06-07
permalink: phd_onboarding_blueprint.html
sidebar: decide_sidebar
---

Every research project — a PhD, a postdoc study, a lab experiment — follows the same path through the research data lifecycle. This page is that path as **one workflow**, not a stack of separate rules. Start at *Plan* and move along; each step tells you what to do and links to the detailed how-to and the tool you need.

## Three pillars travel through every step

- **Data** — your files, stored and backed up (Nextcloud, HPC)
- **Documentation** — what the data mean and how they were made (ELN + metadata + README)
- **Analysis** — the code that turns data into results (Git + JupyterHub/HPC)

Keep the three **linked** — the same IDs everywhere, outputs made by code, a README that maps them — and your results stay reproducible. That linkage, resting on good scientific practice, is the whole point.

## The workflow

<div style="max-width:760px;margin:18px auto;">
<svg width="100%" viewBox="0 0 760 175" xmlns="http://www.w3.org/2000/svg" role="img" aria-labelledby="wf-title wf-desc">
<title id="wf-title">The project workflow along the research data lifecycle</title>
<desc id="wf-desc">Six phases in order — Plan, Collect, Process and Analyse, Preserve, Publish, Reuse — with two gates (G1 when sharing, G2 when publishing) and a loop back to Plan.</desc>
<defs>
<marker id="ah" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse"><path d="M1 1L8 5L1 9" fill="none" stroke="#9aa7b2" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></marker>
<marker id="ahg" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse"><path d="M1 1L8 5L1 9" fill="none" stroke="#c0c8d0" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"/></marker>
</defs>
<line x1="123" y1="82" x2="146" y2="82" stroke="#9aa7b2" stroke-width="1.6" marker-end="url(#ah)"/>
<line x1="246" y1="82" x2="269" y2="82" stroke="#9aa7b2" stroke-width="1.6" marker-end="url(#ah)"/>
<line x1="369" y1="82" x2="392" y2="82" stroke="#9aa7b2" stroke-width="1.6" marker-end="url(#ah)"/>
<line x1="492" y1="82" x2="515" y2="82" stroke="#9aa7b2" stroke-width="1.6" marker-end="url(#ah)"/>
<line x1="615" y1="82" x2="638" y2="82" stroke="#9aa7b2" stroke-width="1.6" marker-end="url(#ah)"/>
<g><rect x="367" y="26" width="27" height="16" rx="8" fill="#5aa02c"/><text x="380" y="38" text-anchor="middle" fill="#fff" font-size="10" font-weight="600">G1</text><line x1="380" y1="42" x2="380" y2="53" stroke="#5aa02c" stroke-width="1.2" stroke-dasharray="2 2"/></g>
<g><rect x="490" y="26" width="27" height="16" rx="8" fill="#5aa02c"/><text x="503" y="38" text-anchor="middle" fill="#fff" font-size="10" font-weight="600">G2</text><line x1="503" y1="42" x2="503" y2="53" stroke="#5aa02c" stroke-width="1.2" stroke-dasharray="2 2"/></g>
<g font-family="inherit">
<rect x="23"  y="55" width="100" height="54" rx="9" fill="#2f6fa8"/><text x="73"  y="86" text-anchor="middle" fill="#fff" font-size="13" font-weight="600">Plan</text><text x="73"  y="127" text-anchor="middle" fill="#667" font-size="10">DMP</text>
<rect x="146" y="55" width="100" height="54" rx="9" fill="#2f6fa8"/><text x="196" y="86" text-anchor="middle" fill="#fff" font-size="13" font-weight="600">Collect</text><text x="196" y="127" text-anchor="middle" fill="#667" font-size="10">ELN &#183; raw</text>
<rect x="269" y="55" width="100" height="54" rx="9" fill="#2f6fa8"/><text x="319" y="79" text-anchor="middle" fill="#fff" font-size="12" font-weight="600">Process &amp;</text><text x="319" y="95" text-anchor="middle" fill="#fff" font-size="12" font-weight="600">Analyse</text><text x="319" y="127" text-anchor="middle" fill="#667" font-size="10">Git &#183; HPC</text>
<rect x="392" y="55" width="100" height="54" rx="9" fill="#2f6fa8"/><text x="442" y="86" text-anchor="middle" fill="#fff" font-size="13" font-weight="600">Preserve</text><text x="442" y="127" text-anchor="middle" fill="#667" font-size="10">Nextcloud</text>
<rect x="515" y="55" width="100" height="54" rx="9" fill="#2f6fa8"/><text x="565" y="86" text-anchor="middle" fill="#fff" font-size="13" font-weight="600">Publish</text><text x="565" y="127" text-anchor="middle" fill="#667" font-size="10">DOI &#183; licence</text>
<rect x="638" y="55" width="100" height="54" rx="9" fill="#2f6fa8"/><text x="688" y="86" text-anchor="middle" fill="#fff" font-size="13" font-weight="600">Reuse</text><text x="688" y="127" text-anchor="middle" fill="#667" font-size="10">next project</text>
</g>
<path d="M688 109 L688 150 L73 150 L73 111" fill="none" stroke="#c0c8d0" stroke-width="1.4" stroke-dasharray="4 3" marker-end="url(#ahg)"/>
<text x="380" y="166" text-anchor="middle" fill="#9aa7b2" font-size="10">the cycle repeats — your output is the next project's input</text>
</svg>
</div>

## The steps

Ordered along the lifecycle. Start at the top; each step links to the detail and the tool.

### 1 &middot; Plan — *before you collect anything*
Write your **Data Management Plan** first — 20 minutes that shapes the whole project. Then create the standard folder structure and agree a naming convention.
&rarr; **[DMP Template](dmp_template.html)**

```
project/
├── README.md          <- the map to everything
├── data/raw/          <- originals, READ-ONLY, never edited
├── data/primary/      <- raw converted to open formats (by code)
├── data/processed/    <- derived data (by code)
├── data/metadata/     <- metadata tables + data dictionary
├── src/  notebooks/   <- the code that makes everything downstream
├── results/  docs/    <- figures, tables, protocols, DMP
```
Naming: `YYYYMMDD_project_sample_condition_type_v01.ext` — no spaces, dates first, one consistent pattern.

### 2 &middot; Collect — *capture and document*
Put raw data in `data/raw/` and **make it read-only** (`chmod -R a-w data/raw/`). Record every run in your **electronic lab notebook** within 48 h, using the *same ID* you'll use everywhere.
&rarr; **[LabFolder](labfolder.html)**

### 3 &middot; Describe — *metadata*
Apply the metadata template at capture time; use your field's controlled vocabulary, not free text. Never leave a blank to mean "not done".
&rarr; **[Metadata Templates](metadata_templates.html)**

### 4 &middot; Process & analyse — *by code only*
Convert raw → primary → processed with scripts (no manual edits); version code in Git; run on JupyterHub/HPC. The rule: if you deleted everything downstream of `data/raw/`, your code in `src/` should regenerate it.
&rarr; **[JupyterHub](jupyterhub.html)** &middot; **[Make your project FAIR](sop_fair_rdm.html)**

### 5 &middot; Preserve — *store and back up*
Keep shared data in a **Nextcloud group folder**; back up raw 3-2-1 (3 copies, 2 media, 1 off-site); archive for the long term.
&rarr; **[Nextcloud](nextcloud.html)**

### 6 &middot; Share — *Gate G1: leaving your private space*
Before data goes to anyone else: run the **FAIR self-check**, clear the **sharing checklist**, and if the data is person-derived, follow the **GDPR** rules (pseudonymise; patient-identifying data stays at UKW).
&rarr; **[FAIR Self-Check](fair_self_check.html)** &middot; **[Sharing & Publishing Checklist](checklist_sharing_publishing.html)** &middot; **[GDPR & Sensitive Data](sop_gdpr_sensitive_data.html)**

### 7 &middot; Publish — *Gate G2: the real publication*
Deposit to a repository with a **DOI** and a **licence** — not a Nextcloud link. Use the two-track approach for sensitive data (open outputs open; individual-level data controlled-access).
&rarr; **[Sharing & Publishing Checklist](checklist_sharing_publishing.html)**

### 8 &middot; Reuse — *the cycle restarts*
Your published, FAIR dataset becomes the Plan-phase input for the next project — yours or a colleague's.
&rarr; **[RDM Lifecycle](sop_rdm_lifecycle.html)**

## The rules of thumb (carry these through every step)

1. **Raw data is sacred** — never edit it; work on copies.
2. **Name things so a stranger understands** — no spaces, dates as `YYYYMMDD`.
3. **One ID everywhere** — filenames, metadata, lab notebook.
4. **Code, don't click** — every result is re-runnable from `src/`.
5. **Write it down as you go** — ELN and README now, not later.
6. **Back up 3-2-1.**
7. **FAIR when you share** — metadata, licence, access level before anything leaves your hands.

*More background and external guidance: [External RDM Resources](external_resources.html) and [The Turing Way](https://book.the-turing-way.org/).*
