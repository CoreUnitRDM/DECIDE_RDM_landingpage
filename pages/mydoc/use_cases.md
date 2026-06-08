---
title: "Use cases & subprojects"
keywords: use cases, subprojects, showcase, FAIR, Infection Atlas, CellWhisperer, cycleHCR, DECIDE
summary: "DECIDE subprojects done the FAIR way — each a worked example of good scientific practice, with its data, documentation, code, DMP and results prepared and interlinked in one project space."
last_updated: 2026-06-07
permalink: use_cases.html
sidebar: decide_sidebar
---

These are DECIDE subprojects taken end-to-end the FAIR way — our show-off examples of research data management and good scientific practice. For each one, a single project space holds everything **prepared and interlinked**: the data, the documentation (ELN + metadata + README), the code, the DMP, and the analysis results — so a collaborator can click from a dataset to the protocol that made it, to the notebook that analysed it, to the figures in the manuscript. Access is governed by **Nextcloud's fine-grained permissions**; request access through the cRDM helpdesk.

## Showcase use cases

<style>
.uc-cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:16px;margin:20px 0 8px;}
.uc-card{display:block;border:1px solid #e3e3e3;border-radius:10px;padding:16px 18px;background:#fff;text-decoration:none;transition:box-shadow .15s ease,border-color .15s ease,transform .15s ease;}
.uc-card:hover{box-shadow:0 5px 16px rgba(0,0,0,.09);border-color:#3b81c4;text-decoration:none;transform:translateY(-1px);}
.uc-card .tag{display:inline-block;font-size:11px;font-weight:700;color:#fff;background:#2f6fa8;border-radius:5px;padding:2px 7px;margin-bottom:8px;letter-spacing:.02em;}
.uc-card .tag.plat{background:#5aa02c;}
.uc-card h3{margin:0 0 5px;font-size:15.5px;color:#16527e;border:0;padding:0;}
.uc-card p{margin:0;font-size:13px;color:#555;line-height:1.5;}
</style>

<div class="uc-cards" markdown="0">
  <a class="uc-card" href="#a03"><span class="tag">A03 · Gomez de Agüero</span><h3>Triple RNA-seq: host · microbiota · pathogen</h3><p>Sharing triple RNA-sequencing data and the HPC setup behind host–bacteria–virus mapping.</p></a>
  <a class="uc-card" href="#a06"><span class="tag">A06 · Faber</span><h3>Decision nodes in co-infection</h3><p>Identifying molecular decision nodes and publishing infection data FAIR.</p></a>
  <a class="uc-card" href="#c03"><span class="tag">C03 · Ibrahim</span><h3>MFA for scRNA-seq</h3><p>A multi-factor analysis framework for multifactorial single-cell RNA-seq.</p></a>
  <a class="uc-card" href="#atlas"><span class="tag plat">Z02 · Saliba</span><h3>Infection Atlas</h3><p>An integrated single-cell expression landscape for DECIDE RNA-seq and single-cell studies.</p></a>
  <a class="uc-card" href="#cellwhisperer"><span class="tag plat">Platform</span><h3>CellWhisperer — talk to your data</h3><p>Explore single-cell datasets in natural language, via Nextcloud Talk.</p></a>
  <a class="uc-card" href="#cyclehcr"><span class="tag plat">Z02 · Platform</span><h3>cycleHCR spatial imaging</h3><p>Highly multiplexed spatial imaging, analysed collaboratively on the HPC.</p></a>
</div>

---

## What every showcase project links to

Each project below points to the same set of FAIR resources (access granted per project via Nextcloud):

- **Project space (Nextcloud)** — data, documentation, code, README, DMP, metadata, results — `<FILL IN cloud link>`
- **Lab notebook (LabFolder)** — protocols and provenance — `<FILL IN>`
- **Analysis (JupyterHub)** — the project's notebooks, runnable on the HPC — `<FILL IN>`
- **Code (Git)** — the versioned pipeline — `<FILL IN>`
- **Results & manuscript** — figures, analysis reports, and the draft that cites them, inside the project space

---

## A03 · Gomez de Agüero — Triple RNA-seq {#a03}

Triple RNA-sequencing of the host–microbiota–pathogen interface, with data sharing and an HPC analysis setup. A worked example of moving large sequencing datasets into the VRC, documenting them, and analysing them reproducibly.
*Links:* `<FILL IN: Nextcloud · LabFolder · JupyterHub · Git>`

## A06 · Faber — Decision nodes in co-infection {#a06}

Epithelial co-infection data prepared for FAIR publication and analysed for the molecular decision nodes that govern infection outcome.
*Links:* `<FILL IN: Nextcloud · LabFolder · JupyterHub · Git>`

## C03 · Ibrahim — MFA framework for scRNA-seq {#c03}

A multi-factor analysis (MFA) framework for multifactorial single-cell RNA-seq experiments — a reusable, documented analysis pipeline.
*Links:* `<FILL IN: Nextcloud · LabFolder · JupyterHub · Git>`

## Z02 · Infection Atlas {#atlas}

The Infection Atlas (Z02, Emanuel Saliba) integrates DECIDE RNA-seq and single-cell studies into one harmonised, FAIR expression landscape. Published datasets can be deposited into or ingested from the Atlas, where they become interactively explorable — a low-barrier entry point to the consortium's data.
*Links:* `<FILL IN: Atlas link · source datasets>`

## CellWhisperer — talk to your data {#cellwhisperer}

CellWhisperer is a multimodal model for single-cell data that lets you **query datasets in natural language** — "show me the cells expressing IFN-stimulated genes in the persistent state" — instead of writing code. It is connected to **Nextcloud Talk** with isolated per-user spaces, supports the Infection Atlas, and lowers the barrier to interacting with DECIDE data. Available to DECIDE users as a cloud app (request access; internal address not published here).
*Source publication:* `<FILL IN>` · *Access:* `<FILL IN: via Nextcloud, request from cRDM>`

## cycleHCR — spatial imaging on the HPC {#cyclehcr}

cycleHCR (cyclic hybridization chain reaction) is a highly multiplexed spatial-imaging method behind Z02's new microscopy / spatial-omics data. The large image datasets are analysed **directly on the HPC through shared JupyterHub notebooks**, in a standardised, collaborative, FAIR way — the same notebook environment any DECIDE member can use.
*Source publication:* `<FILL IN>` · *Links:* `<FILL IN: Nextcloud · JupyterHub notebook>`

---

*New subprojects are added here as they reach FAIR-ready state. To list yours, contact the cRDM helpdesk. Related: [How to start a project](phd_onboarding_blueprint.html) · [JupyterHub](jupyterhub.html) · [External RDM Resources](external_resources.html).*
