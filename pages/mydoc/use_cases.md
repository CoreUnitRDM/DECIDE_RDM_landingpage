---
title: "Use cases & subprojects"
keywords: use cases, subprojects, showcase, FAIR, Infection Atlas, CellWhisperer, cycleHCR, metadata, DECIDE
summary: "DECIDE subprojects done the FAIR way — each with its data, documentation and analysis one click apart."
last_updated: 2026-07-02
permalink: use_cases.html
sidebar: decide_sidebar
---

These are DECIDE subprojects taken end-to-end the FAIR way — our show-off examples of good scientific practice. Where a project is FAIR-ready, its **Data**, **Documentation** and **Analysis** are one click apart: the cloud folder, the protocols, and the runnable notebook. Access is governed by **Nextcloud's fine-grained permissions**; some links are on the university network only (VPN).

<style>
.uc-cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:16px;margin:20px 0 8px;}
.uc-card{border:1px solid #e3e3e3;border-radius:10px;padding:16px 18px;background:#fff;}
.uc-card.soon{opacity:.75;border-style:dashed;}
.uc-card .tag{display:inline-block;font-size:11px;font-weight:700;color:#fff;background:#2f6fa8;border-radius:5px;padding:2px 7px;margin-bottom:8px;letter-spacing:.02em;}
.uc-card .tag.plat{background:#5aa02c;}
.uc-card .tag.soon{background:#9aa7b2;}
.uc-card .tag.tool{background:#7a5195;}
.uc-card h3{margin:0 0 5px;font-size:15.5px;color:#16527e;border:0;padding:0;}
.uc-card p{margin:0;font-size:13px;color:#555;line-height:1.5;}
.uc-links{margin-top:11px;display:flex;flex-wrap:wrap;gap:6px;align-items:center;}
.uc-links a{font-size:12px;font-weight:600;color:#16527e;background:#eef4fa;border:1px solid #d6e4f0;border-radius:6px;padding:3px 9px;text-decoration:none;}
.uc-links a:hover{background:#3b81c4;color:#fff;text-decoration:none;}
.uc-links a.bot{background:#eaf6ec;border-color:#cfe8d4;color:#2f6b39;}
.uc-links a.bot:hover{background:#5aa02c;color:#fff;}
.uc-links .muted{font-size:12px;color:#9aa7b2;}
.uc-note{font-size:12px;color:#9aa7b2;margin:6px 0 0;}
</style>

## Showcase use cases — CRC projects

<div class="uc-cards" markdown="0">
  <div class="uc-card"><span class="tag">A03 · Gomez de Agüero</span><h3>Triple RNA-seq · neonatal skin</h3><p>Colonisation vs infection at the newborn skin–microbiota interface, with data sharing and HPC setup.</p><div class="uc-links"><span class="muted">Links in preparation</span></div></div>
  <div class="uc-card"><span class="tag">A04 · Faber</span><h3>Decision nodes in co-infection</h3><p>Molecular decision nodes in <i>C. difficile</i> / <i>B. theta</i> co-infection, prepared for FAIR publication.</p><div class="uc-links"><span class="muted">Links in preparation</span></div></div>
  <div class="uc-card"><span class="tag">A06 · Löffler</span><h3>Dual RNA-seq · lung</h3><p>Host and pathogen transcriptomes captured in parallel in lung infection.</p><div class="uc-links"><span class="muted">Links in preparation</span></div></div>
  <div class="uc-card"><span class="tag">B01 · Akash (Rudel)</span><h3>Chlamydia host–pathogen interaction</h3><p>Dissecting the Chlamydia–host interface; FAIR data folder in preparation.</p><div class="uc-links"><span class="muted">Links in preparation</span></div></div>
  <div class="uc-card soon"><span class="tag soon">C03 · Kurzai / Ohlsen</span><h3>Coming soon</h3><p>Showcase in preparation — topic being finalised.</p></div>
</div>

## Platform & data services — Z02 / INF

<div class="uc-cards" markdown="0">
  <div class="uc-card"><span class="tag plat">Z02 · Saliba</span><h3>Infection Atlas</h3><p>An integrated single-cell expression landscape for DECIDE RNA-seq and single-cell studies.</p><div class="uc-links"><span class="muted">Atlas link coming</span></div></div>

  <div class="uc-card"><span class="tag plat">Z02 · Beste</span><h3>CellWhisperer — talk to your data</h3><p>Talk to your sequencing data: query single-cell datasets in natural language.</p><div class="uc-links">
    <a href="http://132.187.22.206:8000/hub/user-redirect/lab/tree/Projects_shared/cellwhisperer/cellwhisperer/data">Data</a>
    <a href="https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/index.php/f/3941734">Documentation</a>
    <a href="http://132.187.22.206:5005/">Analysis</a>
    <a class="bot" href="https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/index.php/call/ictm8wrv">Ask the bot</a>
  </div></div>

  <div class="uc-card"><span class="tag plat">Z02 · Beste</span><h3>cycleHCR spatial imaging</h3><p>Highly multiplexed spatial imaging, analysed collaboratively on the HPC.</p><div class="uc-links">
    <a href="https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/index.php/f/3941874">Data</a>
    <a href="https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/index.php/f/3941844">Documentation</a>
    <a href="http://132.187.22.206:8000/hub/user-redirect/lab/tree/Projects_shared/cycleHCR">Analysis</a>
  </div></div>

  <div class="uc-card"><span class="tag plat">Z02 / INF · Immendahl</span><h3>Metadata engine</h3><p>Standardises and enriches metadata across DECIDE datasets — the connective tissue for FAIR.</p><div class="uc-links"><span class="muted">Links in preparation</span></div></div>
</div>

<p class="uc-note">The "ask the bot" link opens a Nextcloud Talk assistant trained on consortium literature. Analysis links (JupyterHub, port 8000 / CellWhisperer, port 5005) run on the HPC and require the university network (VPN).</p>

## Bioinformatics tools

<div class="uc-cards" markdown="0">
  <div class="uc-card"><span class="tag tool">Würzburg Bioinformatics</span><h3>Analysis tools & pipelines</h3><p>Network and omics analysis tools from the Würzburg Bioinformatics group — dynamic network and enzyme analysis (Prosimat), Boolean network simulation (JimenaE), metabolic analysis (YanaSquare), and RNA-seq analysis (RNAanalyzer), plus semi-automated omics and integrated-network pipelines.</p><div class="uc-links">
    <a href="https://bioinfo-wuerz.de/">Open the tools portal</a>
  </div></div>
</div>

---

Need help while working in the VRC? See the [Support &amp; FAQ](faq.html) — real answers from VRC support on transfers, sync, cloud documents, and FAIR analysis.

*New subprojects are added here as they reach FAIR-ready state. To list yours, contact the cRDM helpdesk. Related: [How to start a project](phd_onboarding_blueprint.html) · [JupyterHub](jupyterhub.html) · [External RDM Resources](external_resources.html).*
