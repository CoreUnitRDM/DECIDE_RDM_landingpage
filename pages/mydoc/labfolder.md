---
title: "Practical Guide to Using Electronic Lab Notebooks (ELNs) at Würzburg University"
permalink: labfolder.html
categories: [tutorials, eln]
tags: [eln, labforward, nextcloud, github, metadata, würzburg university]
summary: Learn about elabfolder
sidebar: decide_sidebar
permalink: labfolder.html
folder: mydoc
---

Electronic Lab Notebooks (ELNs) like **Labfolder** help structure and streamline your scientific documentation. This guide gives you **practical steps**, **integration tips**, and **best practices** for using ELNs effectively as part of Würzburg University's **Forschung Digital** services.

---

## 1. Getting Started with Labfolder

Labfolder is the recommended Electronic Lab Notebook (ELN) for researchers at the **University of Würzburg (JMU)** and the **University Hospital Würzburg (UKW)**. It is fully browser-based and hosted on secure university infrastructure.

### A. Registration & Access

#### For UKW Employees

Follow the official UKW registration guide:  
📄 [Step-by-Step UKW Labfolder Guide (PDF)](https://intranet.ukw.de/GB-St/SMI/ForschungsInfrastruktur/Documents/Electronic_lab_notebook-Step_by_Step.pdf) *(accessible from UKW intranet only)*

#### For JMU Employees

Follow the instructions on the official Forschung Digital site:  
🌐 [JMU ELN Registration Instructions](https://www.rz.uni-wuerzburg.de/en/dienste/forschung-digital/electronic-lab-notebooks/)

**Note:**  
JMU employees working on UKW-associated projects may request access to the UKW Labfolder instance by contacting:  
📧 [labfolder@ukw.de](mailto:labfolder@ukw.de)

After registration, your **group administrator** will invite you to the appropriate group workspace. Please follow the guides carefully to avoid technical issues.


### B. Login Links

Use the appropriate login portal depending on your affiliation:

- 🔹 **JMU Labfolder instance**:  
  [https://labfolder.rz.uni-wuerzburg.de/eln/access/login?redirect=1](https://labfolder.rz.uni-wuerzburg.de/eln/access/login?redirect=1)

- 🔹 **UKW Labfolder instance**:  
  [https://labfolder.ukw.de/eln/access/login?redirect=1](https://labfolder.ukw.de/eln/access/login?redirect=1)


### C. Need Help?

- 📘 [Labfolder Quick Guide (PDF)](https://www.med.uni-wuerzburg.de/fileadmin/4302-fdm/Helpdesk/2024-09-16_JK_LabfolderUsageGuide.pdf)
- 📧 **JMU support**: [forschung-digital@uni-wuerzburg.de](mailto:forschung-digital@uni-wuerzburg.de)
- ☎ **Phone (JMU IT support)**: +49 931 31-85050
- 📧 **UKW support**: [labfolder@ukw.de](mailto:labfolder@ukw.de)
- 💬 **Book onboarding or training**: [coreunitrdm@uni-wuerzburg.de](mailto:coreunitrdm@uni-wuerzburg.de)


---

## 2. Connect to Your Project Folder (Nextcloud)

You can store raw data in your group’s Nextcloud research folder and reference it from your ELN.

### Example Workflow:
1. Upload your experimental files to your [Nextcloud RDM project folder](https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/).
2. In Labforward:
   - Add a **File Reference block** in your experiment.
   - Paste the **Nextcloud public link** (with read or edit permissions).
   - Alternatively, include a **mount point path** if synced locally.

💡 *Pro tip*: Organize your Nextcloud folder like `projectname/data/EXP001_raw/`.

---

## 3. Link a GitHub Repository (Optional but Powerful)

To track analysis pipelines and code:

1. Create a GitHub repo (e.g., `exp-xyz-analysis`).
2. In your ELN:
   - Paste the GitHub repo link in the experiment record.
   - Add commit hashes for reproducibility.
3. Consider using **GitHub-Zenodo integration** to archive final versions with DOIs.

---

## 4. Use Metadata Templates and SOPs

Well-structured **metadata** and clear **Standard Operating Procedures (SOPs)** are essential for reproducible, high-quality science. They ensure your experiments are understandable, traceable, and usable by others — or by you months later.

### Why Use Them?

- Metadata links your experiment to samples, data, and analysis.
- SOPs standardize protocols across users and time.
- Together, they make your work **FAIR** (Findable, Accessible, Interoperable, Reusable), improve collaboration, and simplify publication and data reuse.


### Quick Links

- 📋 [Set up group-wide metadata fields](https://support.labforward.io/support/solutions/articles/19000140830-setting-up-a-group-wide-entry-metadata-system)  
- 🧠 [5 Data Management Tips](https://labfolder.com/5-data-management-tips/)  
- 📄 [SOP Guide](https://labfolder.com/de/guide/protokolle-und-sops/)  
- 🎥 [SOP Webinar](https://labfolder.com/webinars/templates/)  
- 🛠 [How to create a template](https://support.labforward.io/support/solutions/articles/19000128979-create-a-template)



### Example Metadata Block

Use a structured block like this at the start of each experiment. You can paste it directly or include it in your ELN template:

```yaml
Project: P23_ImmuneCellFlow
Experiment: EXP001
Date: 2025-07-10
Researcher: Jane Doe
Sample Type: Human PBMCs
Protocol Version: 1.2
Raw Data Path: https://nextcloud.uni-wuerzburg.de/s/abc123
Analysis Repo: https://github.com/labgroup/exp001-analysis

---

## 5. Best Practices for ELNs

1. **Document Regularly**:
   - Update your ELN in real-time to avoid forgetting important details.

2. **Organize Experiments**:
   - Use consistent naming conventions for projects and experiments.

3. **Include Metadata**:
   - Provide as much detail as possible for better data interpretation later.


