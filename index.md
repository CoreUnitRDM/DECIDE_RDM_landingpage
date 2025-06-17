---


title: Research Data Management (RDM) Plan for DECIDE
keywords: DECIDE RDM Plan, Research Data Management, FAIR principles, Data Lifecycle
last_updated: June 13, 2025
tags: [RDM Plan, DECIDE, Data Management, FAIR]
summary: Explore the RDM plan of the DECIDE project, including data organizations, FAIR data management, and long-term goals for a FAIR and secure data lifecycle.
sidebar: decide_sidebar
permalink: index.html
folder: mydoc


---


## Roles and Responsibilities
- **Thomas Dandekar**, Principal Investigator (PI) (thomas.dandekar@uni-wuerzburg.de): Overall project oversight, data governance, final approvals.
- **Johannes Balkenhol**, RDM Lead & Cloud Admin (johannes.balkenhol@uni-wuerzburg.de): Day-to-day RDM operations, integrated network analysis, cloud infrastructure management.
- **Hamidreza Alimohammadi**, cRDM Specialist & Cloud Admin (Alimohamma_H@ukw.de, coreunitrdm@uni-wuerzburg.de): Metadata standards, data format conversion, metadata search, organizational guidelines, support via [cRDM](https://www.med.uni-wuerzburg.de/fdm/).
- **Juan Prada**, Cloud Administrator (juan.prada_salcedo@uni-wuerzburg.de): Nextcloud administration, LLM, and support.


## DECIDE RDM
The DECIDE consortium recognizes the critical role of effective Research Data Management (RDM) in achieving its scientific goals. By adhering to FAIR principles (Findable, Accessible, Interoperable, and Reusable), DECIDE’s RDM plan fosters collaboration, enhances data quality, and promotes long-term data accessibility.
For additional references, visit the [Knowledge Base on RDM](https://knowledgebase.nfdi4microbiota.de/Getting-Started/01-introduction.html).


### 0. Data Management Plan
Plan how you’ll handle your data before starting. Use our [RDM planner](/pages/mydoc/rdm_planer2.md) to define data type, size, storage solution, sharing, and backup.


### 1. Data Organization
Whether local or in the cloud, **agreeing on a consistent data structure** is crucial. While international standards provide recommendations, the DECIDE consortium must define and document its own standard structure to ensure interoperability and scalability, especially when handling big data and on-the-fly processing.
- **Lesson on Data Organization:** [Zenodo DOI:10.4126/FRL01-006484175](https://doi.org/10.4126/FRL01-006484175)


#### 1.1 Folder Structure
Adapted from NFDI microbiota:
```
project_id/
├── data/
│   ├── raw_data/
│   ├── processed_data/
|   └── metadata_file.xml
├── documentation/
|   ├── labfolder_link.ln
│   ├── literature/
│   ├── manuscript/
│   └── figures/
├── analysis/
├── results/
├── scripts/
├── DMP
└── README.md
```


#### 1.2 File Naming
Follow NFDI guidelines:
```
<YYYY-MM-DD>_<project_id>_<data_type>_<description>_<version>.<txt>
```
**Examples:**
- `2025-01-26_DECIDE123_RNAseq_raw_reads_v1.fastq`
- `2025-01-26_DECIDE123_image_cell_structure_v1.tiff`

**Tips:**
- Use only letters, numbers, `_`, and `-`  
- Document conventions in `README.md`


### 2. Data Generation
Data generation starts in the lab—through experiments, instruments, or from external databases. All **raw data** should be captured as early as possible and documented in the **[Electronic Lab Notebook (ELN)](https://www.rz.uni-wuerzburg.de/dienste/forschung-digital/eln/)** or other structured formats.

- Basic metadata (**what, when, how**) must be recorded at the point of generation.
- Use ELN templates, structured Excel sheets, or XML/JSON files attached to the data.
- For data from public databases, note the **source**, **access date**, and **version**.
- Ensure consistent naming and folder conventions to support later analysis and reproducibility.


### 3. File Formats
- **HDF5** / **AnnData (.h5ad)** for single-cell and hierarchical data  
- **FASTQ**, **BAM**, **VCF**, **mzML** for sequencing and multi-omics  
- **CSV**, **TSV**, **Loom** for tabular and matrix data  
- **TIFF**, **OME-TIFF**, **OME-ZARR** for imaging, incl. flow chamber videos  
- Convert proprietary formats to open standards **with metadata preserved**


### 4. Data Collection, Storage & Sharing
- **Primary/Raw Data:** Generated in-lab, recorded in ELN, stored on institute drive.
- **Active Data:** Stored, shared, backed up via [Nextcloud](https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/).
- **Archiving:** 10 years long-term backup via University of Würzburg Data [Archiving Server](https://www.rz.uni-wuerzburg.de/dienste/rzserver/svb/archivserver/).
- **External Repositories: e.g.**  
  - [ArrayExpress](https://www.ebi.ac.uk/biostudies/arrayexpress)  
  - [NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/)
  - [Single Cell Expression Atlas](https://www.ebi.ac.uk/gxa/sc/home) 
- **Security Measures:** Regular backups, RZ security standards, controlled access policies.


### 5. Documentation & Version Control
- **[Electronic Lab Notebook (ELN)](https://www.rz.uni-wuerzburg.de/dienste/forschung-digital/eln/):**  
  Use eLabFTW (eLabFolder) to document SOPs, protocols, experimental parameters, and data links in a structured and timestamped format.
- **Version Control with [GitHub](https://github.com/) and [Nextcloud](https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/):**
  Host and manage files, code, scripts, pipelines, and collaborative documents. Use branches, pull requests, commits, and issue tracking to ensure reproducibility and transparent development.
- **Persistent Archiving with [Zenodo](https://zenodo.org/):**  
  Archive published datasets, software, and GitHub repositories with DOIs to enable citation and long-term accessibility.
- **Workflow Sharing:**  
  Use [nextflow](https://www.nextflow.io/) for reproducible pipeline execution and [protocols.io](https://www.protocols.io/) to publish and share detailed experimental protocols and SOPs.


### 6. Metadata Management
- **[Metadata Templates](https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/index.php/s/c8yD3ddfJ3xsAjb) developed by DECIDE consoriutm aligned along  NFDI4Microbiota recommendations 
- **Metadata Standards Repository:** Use [NFDI4Microbiota/MetadataStandards](https://github.com/NFDI4Microbiota/MetadataStandards).



### 7. Data Analysis Infrastructure
- **[HPC Bioinfo (JupyterHub)](/pages/mydoc/jupyterhub.md) and Uni Würzburg HPC [Julia I/II](https://www.rz.uni-wuerzburg.de/dienste/rzserver/high-performance-computing/):**
  - Usage: Julia I/II HPC and Bioinformatics HPC (requires Uni ID, VPN, and registration).  
  - Connection to Nextcloud via [`rclone`](https://rclone.org/) or WebDAV packages in [R](https://cran.r-project.org/web/packages/webdav/index.html)/[Python](https://pypi.org/project/webdavclient3/).
- **[Prosimat](https://prosimat.bioinfo-wuerz.eu/) & [Cat-E](https://cat-e.bioinfo-wuerz.eu/):** Tools für dynamische Netzwerk- und Enzymanalyse.
- **DECIDE Analysis Pipelines:** Automatisierte Workflows auf GitHub.


### 8. Licensing
Follow standard Creative Commons licenses (e.g., CC BY, CC 0) to balance reuse and IP protection. See [Licensing Guidelines](https://knowledgebase.nfdi4microbiota.de/RDM-Share/licenses.html).


### 9. Data Continuation & Integration
- [Single Cell Infection Atlas: Z-project](/pages/mydoc/infection_atlas.md)
- Integrated & Dynamic Network Analysis (INF Project)

---

## Summary: Current Virtual Research Campus (VRC) Architecture  
_Architecture of the Virtual Research Campus (VRC): From the Perspective of Researchers_  
© Core Unit RDM

![Architecture of the Virtual Research Campus (VRC)](/images/2025-06-02_JB_VRC-Wuerzburg_CurrentUserPerspective.png)

- **Data Generation & Documentation**  
  - Raw data is generated in the lab (animal experiments, cell culture, measurement instruments).  
  - Documentation via eLabFolder: SOPs, protocols, parameters, and links to each data file.  
  - Metadata and scripts are generated in parallel (Python, R, MATLAB…).
- **RDM Knowledge Base & Standards**  
  - Central templates for folder structure, file naming, and metadata (NFDI/EU-compliant).  
  - FAIR checklists for formats, versioning tools (Git, Zenodo, Nextcloud).
- **Organized Locally or in the Cloud**  
  - Project folders are created using standard templates.  
  - Consistency is prioritized over storage location.
- **Cloud Sync & Data Backup**  
  - WebDAV connection mirrors folders to the private cloud.  
  - Automatic backups and snapshot mechanisms.
- **Computing (HPC)**  
  - Julia II and Bioinformatics HPC systems are available to users at JMU.  
  - Cloud data can be mounted into the compute system using APIs such as WebDAV.
- **GitHub for Scripts & Collaboration**  
  - Development directly in GitHub repositories with version control and issue tracking.
- **FAIR Publication**  
  - Export of selected datasets with DOI, open licenses, and complete metadata.

**Added Value:** Time savings, security, reproducibility, flexibility, transparency.


## Long-Term Goals
- Vollständige Integration in eine Virtual Research Campus (VRC).  
- Förderung cross-projektiver Datenintegration zur Identifikation molekularer Entscheidungs-punkte.


## Challenges and Solutions in RDM for DECIDE

### Challenges  
- **Data Complexity:** Large multi-omics datasets and infection research data.  
- **Standardization:** Consistent metadata across different work areas.  
- **Compliance:** GDPR compliance for data security and privacy.  

### Solutions  
- Standardized metadata templates and FAIR checklists.  
- Centralized storage and systematic workflows.  
- Training programs on ELN and RDM tools.

---

## Resources & Good Practices
- [Brief Guide RDM](https://zenodo.org/records/4000989)  
- [The Carpentries: Good-enough practices for data management](https://carpentries-lab.github.io/good-enough-practices/02-data_management.html#create-the-data-you-wish-to-see-in-the-world))
- [Knowledge Base on RDM](https://knowledgebase.nfdi4microbiota.de/Research-Data-Management/01-introduction.html)
- [Metadata Standards Repository](https://github.com/NFDI4Microbiota/MetadataStandards)
- [Data Organization](https://doi.org/10.4126/FRL01-006484175)
- [File Naming Guidelines by ELIXIR Belgium](https://rdm.elixir-belgium.org/file_naming)
- [Folder Structure Recommendations by ELIXIR Belgium](https://rdm.elixir-belgium.org/folder_structure)
- [NFDI4Plants Data Plan Tool](https://www.nfdi4plants.de/dataplan/)
