---
title: "Start here"
keywords: RDM, FAIR, quick start, PhD, onboarding, overview, VRC, pillars
summary: "The 5-minute version: why research data management pays off for you, the rules of thumb, and where to go next."
last_updated: 2026-06-07
permalink: index.html
sidebar: decide_sidebar
---

Research data management sounds like admin. It isn't — it's how you protect your thesis, publish faster, and turn your results into something the world can trust and build on. **This page is the 5-minute version.** Skim it, remember the rules of thumb, and follow a link only when you want the detail.

<p style="margin:18px 0;"><img src="/images/onboarding_flow_bold.svg" alt="From new scientist to FAIR-informed researcher: register, plan, train, connect, publish" style="width:100%;max-width:760px;"></p>

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
  <a class="sh-card" href="phd_onboarding_blueprint.html"><div class="sh-ico"><i class="fa fa-rocket"></i></div><h3>Start a project</h3><p>The day-one workflow, step by step.</p></a>
  <a class="sh-card" href="sop_fair_rdm.html"><div class="sh-ico"><i class="fa fa-check-circle"></i></div><h3>Make my project FAIR</h3><p>Tool-by-tool FAIR steps, plus a quick self-check.</p></a>
  <a class="sh-card" href="checklist_sharing_publishing.html"><div class="sh-ico"><i class="fa fa-share-alt"></i></div><h3>Share or publish data</h3><p>What to verify before data leaves your hands.</p></a>
  <a class="sh-card" href="dmp_template.html"><div class="sh-ico"><i class="fa fa-file-text-o"></i></div><h3>Write my DMP</h3><p>A data management plan, pre-filled for the VRC.</p></a>
  <a class="sh-card" href="use_cases.html"><div class="sh-ico"><i class="fa fa-cubes"></i></div><h3>See it done</h3><p>Showcase subprojects, fully FAIR.</p></a>
  <a class="sh-card" href="sop_gdpr_sensitive_data.html"><div class="sh-ico"><i class="fa fa-lock"></i></div><h3>Handle sensitive data</h3><p>GDPR, patient data, and the UKW boundary.</p></a>
</div>

## Our approach: the VRC and three pillars

DECIDE RDM rests on a simple model.

<div style="max-width:760px;margin:18px auto;">
<svg width="100%" viewBox="0 0 760 292" xmlns="http://www.w3.org/2000/svg" role="img" aria-labelledby="vrc-t vrc-d">
<title id="vrc-t">The DECIDE VRC: the researcher journey, the cRDM pillars, and their foundation</title>
<desc id="vrc-d">Top: the researcher journey — Data (I find it), Documentation (I understand it), Analysis (I reproduce it). Middle: the cRDM service pillars — Knowledgebase, Infrastructure (the VRC), Training. Bottom: a foundation of good scientific practice, data sovereignty, data security, and collaboration.</desc>
<defs>
<marker id="va" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse"><path d="M1 1L8 5L1 9" fill="none" stroke="#9aa7b2" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/></marker>
</defs>
<text x="50" y="16" font-size="11" font-weight="700" fill="#2f6fa8" letter-spacing="0.5">RESEARCHER JOURNEY — what every project does</text>
<g font-family="inherit">
<rect x="50" y="28" width="198" height="60" rx="10" fill="#1A3A5C" stroke="#2B6CB0"/>
<text x="149" y="54" text-anchor="middle" fill="#fff" font-size="15" font-weight="600">Data</text>
<text x="149" y="74" text-anchor="middle" fill="#9fc3e8" font-size="11" font-style="italic">&#8220;I find it&#8221;</text>
<rect x="281" y="28" width="198" height="60" rx="10" fill="#1A3A5C" stroke="#2B6CB0"/>
<text x="380" y="54" text-anchor="middle" fill="#fff" font-size="15" font-weight="600">Documentation</text>
<text x="380" y="74" text-anchor="middle" fill="#9fc3e8" font-size="11" font-style="italic">&#8220;I understand it&#8221;</text>
<rect x="512" y="28" width="198" height="60" rx="10" fill="#1A3A5C" stroke="#2B6CB0"/>
<text x="611" y="54" text-anchor="middle" fill="#fff" font-size="15" font-weight="600">Analysis</text>
<text x="611" y="74" text-anchor="middle" fill="#9fc3e8" font-size="11" font-style="italic">&#8220;I reproduce it&#8221;</text>
</g>
<line x1="250" y1="58" x2="279" y2="58" stroke="#9aa7b2" stroke-width="1.8" marker-end="url(#va)"/>
<line x1="481" y1="58" x2="510" y2="58" stroke="#9aa7b2" stroke-width="1.8" marker-end="url(#va)"/>
<text x="50" y="112" font-size="11" font-weight="700" fill="#5aa02c" letter-spacing="0.5">ENABLED BY THE cRDM PILLARS &#8595;</text>
<g font-family="inherit">
<rect x="50" y="124" width="198" height="58" rx="10" fill="#1A3A5C" stroke="#2B6CB0"/>
<text x="149" y="150" text-anchor="middle" fill="#fff" font-size="15" font-weight="600">Knowledgebase</text>
<text x="149" y="169" text-anchor="middle" fill="#9fc3e8" font-size="11">this site &#183; SOPs &#183; standards</text>
<rect x="281" y="124" width="198" height="58" rx="10" fill="#1A3A5C" stroke="#2B6CB0"/>
<text x="380" y="150" text-anchor="middle" fill="#fff" font-size="15" font-weight="600">Infrastructure</text>
<text x="380" y="169" text-anchor="middle" fill="#9fc3e8" font-size="11">the VRC &#183; cloud &#183; HPC &#183; ELN</text>
<rect x="512" y="124" width="198" height="58" rx="10" fill="#1A3A5C" stroke="#2B6CB0"/>
<text x="611" y="150" text-anchor="middle" fill="#fff" font-size="15" font-weight="600">Training</text>
<text x="611" y="169" text-anchor="middle" fill="#9fc3e8" font-size="11">WueCampus &#183; workshops</text>
</g>
<rect x="40" y="216" width="680" height="58" rx="12" fill="#3f7a3f"/>
<text x="380" y="240" text-anchor="middle" fill="#fff" font-size="12" font-weight="700">Foundation &#8212; good scientific practice</text>
<text x="380" y="260" text-anchor="middle" fill="#dff0d8" font-size="11">data sovereignty &#183; data security &#183; collaborative, reproducible research</text>
</svg>
</div>

As a researcher you move your work through three pillars — **Data** (find it), **Documentation** (understand it), **Analysis** (reproduce it). cRDM makes that possible through three service pillars: a **Knowledgebase** (this site — SOPs and standards), the **Infrastructure** (the **Virtual Research Campus**: shared Nextcloud, JupyterHub, HPC and ELN, run together with Bioinformatics and combined with RZ/SMI services), and **Training** (WueCampus, workshops, consulting).

All of it rests on good scientific practice — and on three things the VRC is built to protect: **data sovereignty** (your data stays under your control, with fine-grained access you set), **data security** (patient-identifying data never leaves UKW — the VRC is for research data, not patient data), and **collaborative, reproducible research**.

This hub is run by the **cRDM — core unit Research Data Management** of the Medical Faculty ([med.uni-wuerzburg.de/fdm](https://www.med.uni-wuerzburg.de/fdm/)). Using the VRC services means agreeing to the cRDM terms of use (Nutzungsordnung): [Nutzungsordnung cRDM (PDF, DE)](https://www.med.uni-wuerzburg.de/fileadmin/07030400/2026/2026-03_Nutzungsordnung_cRDM_de.pdf).
