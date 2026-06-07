---
title: "Start here"
keywords: RDM, FAIR, quick start, PhD, onboarding, overview
summary: "The 5-minute version: why research data management pays off for you, the rules of thumb, and where to go next."
last_updated: 2026-06-07
permalink: start_here.html
sidebar: decide_sidebar
---

Research data management sounds like admin. It isn't — it's how you protect your thesis, publish faster, and turn your results into something the world can trust and build on. **This page is the 5-minute version.** Skim it, remember the rules of thumb, and follow a link only when you want the detail.

## Why bother? (the 30-second case)

Good RDM isn't paperwork for funders — it's leverage for *your* research:

- **Your thesis is safer.** Backed-up, well-named, documented data can't be lost, corrupted, or rendered meaningless the day you graduate and leave the lab.
- **You work faster.** Find any file in seconds; re-run an analysis with one command instead of wondering "which Excel did I edit last?"
- **Your results are provable.** A reproducible pipeline *is* the proof reviewers ask for — raw data to final figure, traceable end to end.
- **Better, sharper science.** Standardised, FAIR data is comparable across studies, generalisable, and reusable — it's what makes meta-analyses, automation, and machine learning possible. Messy data can't do any of that.
- **You collaborate without friction.** Shared standards mean a colleague — or future-you — understands your data without a 30-minute explanation.
- **It compounds.** Today's clean dataset becomes tomorrow's citable publication (with a DOI) and the next student's starting point. That's transparent, open, modern science — and it travels globally.

> In one line: a little structure now buys you speed, trust, and reusable results later. And **FAIR is only the *exit* standard** — you owe nothing while data sits in your private space; the rules kick in when you share.

## The rules of thumb

Memorise these seven. They're ~80% of the benefit for ~20% of the effort. The "how to do each properly" lives in the detailed pages below — come back for them when you need them.

1. **Raw data is sacred** — never edit it. Keep originals read-only, back them up, work on copies.
2. **Name things so a stranger understands** — no spaces, dates as `YYYYMMDD`, one consistent pattern.
3. **One ID everywhere** — the same sample/subject ID in your filenames, your metadata, and your lab notebook.
4. **Code, don't click** — every step from raw to result is a script you can re-run, not a manual edit you can't.
5. **Write it down as you go** — the lab-notebook entry and the README happen now, not "later".
6. **Back up 3-2-1** — 3 copies, on 2 kinds of media, 1 off-site.
7. **FAIR when you share** — metadata, a licence, and the right access level before anything leaves your private space.

## Where to next?

Pick the card that matches what you're doing. Each opens the full how-to.

<style>
.sh-cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:16px;margin:22px 0 8px;}
.sh-card{display:block;border:1px solid #e3e3e3;border-radius:10px;padding:18px 20px;background:#fff;text-decoration:none;transition:box-shadow .15s ease,border-color .15s ease,transform .15s ease;}
.sh-card:hover{box-shadow:0 5px 16px rgba(0,0,0,.09);border-color:#3b81c4;text-decoration:none;transform:translateY(-1px);}
.sh-card .sh-ico{font-size:22px;color:#3b81c4;margin-bottom:9px;}
.sh-card h3{margin:0 0 5px;font-size:16px;color:#16527e;border:0;padding:0;}
.sh-card p{margin:0;font-size:13.5px;color:#555;line-height:1.5;}
</style>

<div class="sh-cards" markdown="0">
  <a class="sh-card" href="phd_onboarding_blueprint.html"><div class="sh-ico"><i class="fa fa-rocket"></i></div><h3>Start my PhD project</h3><p>The day-one onboarding blueprint, step by step.</p></a>
  <a class="sh-card" href="sop_fair_rdm.html"><div class="sh-ico"><i class="fa fa-check-circle"></i></div><h3>Make my project FAIR</h3><p>Tool-by-tool FAIR steps, plus a quick self-check.</p></a>
  <a class="sh-card" href="checklist_sharing_publishing.html"><div class="sh-ico"><i class="fa fa-share-alt"></i></div><h3>Share or publish data</h3><p>What to verify before data leaves your hands.</p></a>
  <a class="sh-card" href="dmp_template.html"><div class="sh-ico"><i class="fa fa-file-text-o"></i></div><h3>Write my DMP</h3><p>A data management plan, pre-filled for the VRC.</p></a>
  <a class="sh-card" href="metadata_templates.html"><div class="sh-ico"><i class="fa fa-table"></i></div><h3>Plan my metadata</h3><p>The template and the right standard for your field.</p></a>
  <a class="sh-card" href="sop_gdpr_sensitive_data.html"><div class="sh-ico"><i class="fa fa-lock"></i></div><h3>Handle sensitive data</h3><p>GDPR, patient data, and the UKW boundary.</p></a>
</div>

## The infrastructure behind this: the VRC

This knowledge hub is run by the **cRDM — core unit Research Data Management** of the Medical Faculty ([med.uni-wuerzburg.de/fdm](https://www.med.uni-wuerzburg.de/fdm/)). Together with the **Bioinformatics** group we operate the shared **Nextcloud, JupyterHub, and HPC**, and combine them with the **Rechenzentrum (RZ)** and **SMI** services into one **Virtual Research Campus (VRC)** — a single, joined-up environment for your data from planning to publication. Seamless connectors between these services are actively in the making.

Using the VRC services means agreeing to the cRDM terms of use (Nutzungsordnung): [Nutzungsordnung cRDM (PDF, DE)](https://www.med.uni-wuerzburg.de/fileadmin/07030400/2026/2026-03_Nutzungsordnung_cRDM_de.pdf).
