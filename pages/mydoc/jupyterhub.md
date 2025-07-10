---
title: "Getting Started with JupyterHub"
categories: [tutorials, jupyterhub]
tags: [jupyterhub, data analysis, vpn, würzburg, hpc]
sidebar: decide_sidebar
permalink: jupyterhub.html
folder: mydoc
---

# Getting Started with JupyterHub at Würzburg University

JupyterHub provides a collaborative and user-friendly environment for **data analysis**, **computational workflows**, and **notebook-based research**, specifically tailored for the Bioinformatics team at Würzburg University. It runs directly on the department's HPC environment and can also serve as a gateway to other high-performance resources.

---

## 1. Prerequisite: Connect to the VPN

Before accessing JupyterHub, you must first connect to the **University of Würzburg VPN**.

### How to Connect:

1. Visit the [VPN Guide – Würzburg University](https://www.rz.uni-wuerzburg.de/dienste/it-sicherheit/vpn/)
2. Follow instructions for your system:
   - Windows / macOS / Linux / iOS / Android
3. Log in using your university credentials.

---

## 2. Request Access to JupyterHub and HPC

JupyterHub runs on the Bioinformatics HPC system. Before using it or accessing the University’s central HPC ("Julia 2"), please contact:

- **Prof. Thomas Dandekar** – [dandekar@biozentrum.uni-wuerzburg.de](mailto:dandekar@biozentrum.uni-wuerzburg.de)
- **Johannes Balkenhol** - [johannes.balkenhol@uni-wuerzburg.de](mailto:johannes.balkenhol@uni-wuerzburg.de)
- **Stefan Obermeier** – [stefan.obermeier@biozentrum.uni-wuerzburg.de](mailto:stefan.obermeier@biozentrum.uni-wuerzburg.de)

For using the university-wide HPC "Julia 2", visit:  
🔗 [HPC at Würzburg University](https://www.rz.uni-wuerzburg.de/dienste/rzserver/high-performance-computing/)

---

## 3. Log In to JupyterHub

Once VPN is connected and access is granted:

1. Open your browser and go to:  
   🔗 [https://jupyterhub.uni-wuerzburg.de/](https://jupyterhub.uni-wuerzburg.de/)
2. Alternatively, access via **Nextcloud**:  
   - Look for the **JupyterHub icon** listed as an external service.
3. Or ask the Bioinformatics administrators for the internal IP if needed.
4. Log in using your **University of Würzburg credentials**.

---

## 4. Tools, Notebooks, and Resources

### A. Widgets & Helper Scripts

Helpful scripts for:

- Mounting cloud data
- Extracting metadata
- Visualizing datasets

🔗 [GitHub – CoreUnitRDM Tools](https://github.com/CoreUnitRDM)

### B. Pre-built Notebooks

Get started quickly with:

- Data exploration workflows
- Statistical analysis pipelines
- Visualization templates

🗂️ Ask an administrator for the current shared notebook collection.

---

## 5. Best Practices for JupyterHub Users

- **Organize Your Workspace**  
  Use folders to keep each project clean and separated.

- **Document Code and Results**  
  Add Markdown cells and comments throughout your notebook.

- **Backup Frequently**  
  Download notebooks or sync to your Nextcloud folder.

- **Use Resources Considerately**  
  Avoid blocking shared memory or long-running processes unnecessarily.

---

## 6. Learn More: Official JupyterHub Resources

- 🌐 [What is JupyterHub?](https://jupyterhub.readthedocs.io/en/stable/)
- 📘 [Intro to Jupyter Notebooks](https://jupyter-notebook.readthedocs.io/en/stable/)

---

{% include links.html %}
