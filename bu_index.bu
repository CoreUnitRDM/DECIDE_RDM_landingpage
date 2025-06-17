---
title: Research Data Management (RDM) Plan for DECIDE
keywords: DECIDE RDM Plan, Research Data Management, FAIR principles, Data Lifecycle
last_updated: January 26, 2025
tags: [RDM Plan, DECIDE, Data Management, FAIR]
summary: Explore the RDM plan of the DECIDE project, including file formats, metadata management, and long-term goals for a FAIR and secure data lifecycle.
sidebar: decide_sidebar
permalink: index.html
folder: mydoc

---

## Summary of the DECIDE Project and Focus Areas

Infectious diseases pose a global challenge, exacerbated by multidrug resistance and emerging pathogens. The DECIDE project aims to revolutionize infection therapy by shifting the therapeutic focus from pathogens to optimizing the host's immune response. Researchers employ a multilayered systems approach to explore three key areas:

1. **Containment vs. Active Infection**: Investigating the host's response to first contact with a pathogen.
2. **Acute vs. Chronic Infection**: Understanding factors influencing infection persistence or resolution.
3. **Localized vs. Systemic Spread**: Exploring the mechanisms behind infection dissemination.

This innovative framework addresses critical gaps in host-pathogen dynamics to inform novel prevention and treatment strategies.

---

## DECIDE RDM Plan

The DECIDE consortium recognizes the critical role of effective Research Data Management (RDM) in achieving its scientific goals. By adhering to FAIR principles (Findable, Accessible, Interoperable, and Reusable), DECIDE’s RDM plan fosters collaboration, enhances data quality, and promotes long-term data accessibility.

For additional references, visit the [Knowledge Base on RDM](https://knowledgebase.nfdi4microbiota.de/Getting-Started/01-introduction.html).


### 1. File Formats
- Recommended formats include **HDF5** for hierarchical data, **FASTQ** for sequencing data, **CSV** for tabular data, and other standard formats for multi-omics and infection research datasets.
- Proprietary formats should be converted while preserving original metadata.


### 2. Data Collection
- **Primary and Raw Data:**  
  Primary data is processed at the institute by the data generator.
- **Data Storage and Sharing:**  
  Active data is stored and shared in [Nextcloud](https://www.coreunitrdm.biozentrum.uni-wuerzburg.de/).
- **Data Archiving:**  
  Long-term archiving is managed using the University of Würzburg’s [Data Archiving Service](https://www.rz.uni-wuerzburg.de/dienste/rzserver/archivierung-von-daten/).
- **External Archives:**  
  - [Single Cell Expression Atlas](https://www.ebi.ac.uk/gxa/sc/home)  
  - [ArrayExpress](https://www.ebi.ac.uk/biostudies/arrayexpress)  
  - [NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/)
- **Security Measures:**  
  Regular backups, RZ security standars, and controlled access are implemented.


### 3. Documentation
- **ELN**:
   [ELN Uni Würzburg](https://www.rz.uni-wuerzburg.de/dienste/forschung-digital/eln/): For systematic data collection and laboratory documentation.
- **Github**:
   [GitHub](https://github.com/CoreUnitRDM): Hosting pipelines, workflows, and SOPs for computational and experimental analyses.


### 4. Metadata Management
- Standardized metadata collection using the **Nextcloud metadata app**, aligned with [NFDI4Microbiota](https://knowledgebase.nfdi4microbiota.de/Research-Data-Management/03-md.html).
- Researchers are encouraged to use [Metadata Standards Repository](https://github.com/NFDI4Microbiota/MetadataStandards) to find guidelines specific to their data type.


### 5. Administrative Recommendations
- **File Naming Guidelines**:  
  Follow best practices outlined by [ELIXIR Belgium](https://rdm.elixir-belgium.org/file_naming) to enhance traceability and clarity.
    **Format:**  
  `<project_id>_<data_type>_<description>_<date>_<version>.<extension>`

  **Example File Names:**  
  - **Raw sequencing data**:  
    `DECIDE123_RNAseq_raw_reads_20250126_v1.fastq`
  - **Processed data**:  
    `DECIDE123_RNAseq_aligned_data_20250126_v2.hdf5`
  - **Metadata file**:  
    `DECIDE123_metadata_sample_info_20250126_v1.csv`
  - **Microscopy image**:  
    `DECIDE123_image_cell_structure_20250126_v1.tiff`
  - **Analysis script**:  
    `DECIDE123_analysis_normalization_20250126_v3.py`

  **Key Tips:**
  - Avoid special characters; use only letters, numbers, underscores (`_`), and hyphens (`-`).
  - Be consistent across all project files.
  - Document file naming conventions in the project README.md for clarity.

- **Folder Structure**:  
  Organize data project-wise with the following structure (adaptable to [ELIXIR Belgium recommendations](https://rdm.elixir-belgium.org/folder_structure)):

    <table>
        <tr><td><b>project_id/</b></td></tr>
        <tr><td>&emsp;├── <b>data/</b></td></tr>
        <tr><td>&emsp;&emsp;└── <b>raw_data/</b></td></tr>
        <tr><td>&emsp;&emsp;└── <b>processed_data/</b></td></tr>
        <tr><td>&emsp;├── <b>documents/</b></td></tr>
        <tr><td>&emsp;&emsp;└── <b>literature/</b></td></tr>
        <tr><td>&emsp;&emsp;└── <b>manuscript/</b></td></tr>
        <tr><td>&emsp;&emsp;└── <b>figures/</b></td></tr>
        <tr><td>&emsp;├── <b>analysis/</b></td></tr>
        <tr><td>&emsp;├── <b>results/</b></td></tr>
        <tr><td>&emsp;├── <b>scripts/</b></td></tr>
        <tr><td>&emsp;├── <b>labfolder_link.ln</b></td></tr>
        <tr><td>&emsp;├── <b>DMP (data management plan)</b></td></tr>
        <tr><td>&emsp;├── <b>metadata_file.xml</b></td></tr>
        <tr><td>&emsp;├── <b>README.md (project description and licensing)</b></td></tr>
    </table>

- **DMP**: 
    Optionally, generate a data management file using the [NFDI4Plants Data Plan Tool](https://www.nfdi4plants.de/dataplan/).

### 6. Data Generation and Analysis

- **JupyterHub**:  
  Multi-omics datasets are processed on secure HPC servers with 128 CPU cores, GPU A100, and 20TB storage. Interactive workflows are supported through [JupyterHub](/pages/mydoc/jupyterhub.md).

- **Prosimat**:  
  Explore multi-omics data analysis using [Prosimat](https://prosimat.bioinfo-wuerz.de/).

- **Cat-E**:  
  Comprehensive catabolic enzyme analysis tools are available at [Cat-E](https://cat-e.bioinfo-wuerz.de/).

- **Analysis Pipelines**:  
  Streamline your workflows with [DECIDE Analysis Pipelines](https://github.com/CoreUnitRDM).

- **Further Bioinformatics Tools**:  
  Access additional bioinformatics resources at [Bioinformatics Computing](https://www.biozentrum.uni-wuerzburg.de/bioinfo/computing/).


### 7. Licensing
- Ensure appropriate licensing for datasets and tools to enable reuse while protecting intellectual property. Follow standard guidelines for Creative Commons (e.g., CC BY or CC0) [Licensing](https://knowledgebase.nfdi4microbiota.de/RDM-Share/licenses.html)


### 8. Data Continuation
- [Single Cell Infection Atlas: Z-project](infection_atlas.html)  
- Robust protein interaction inference on single cell basis: Integrated & Dynamic Network Analysis (INF Project)

### 9. Long-Term Goals
- Transition to a fully integrated Virtual Research Environment (VRE) for seamless data sharing and collaboration.
- Promote cross-project data integration to identify molecular decision points in infections.

---

## Challenges and Solutions in RDM for DECIDE

### Challenges
- **Data Complexity**: Managing large-scale multi-omics datasets and infection research data.
- **Standardization**: Ensuring consistent metadata across diverse research areas.
- **Compliance**: Addressing GDPR requirements for data security and privacy.

### Solutions
- Use of the metadata templates for standardized metadata collection.
- Centralized data storage in a cloud and systematic workflows.
- Training programs on ELNs and data management tools.

---

## References and Resources

### Key References
- [Knowledge Base on RDM](https://knowledgebase.nfdi4microbiota.de/Research-Data-Management/01-introduction.html)
- [Metadata Standards Repository](https://github.com/NFDI4Microbiota/MetadataStandards)

### Resources for Best Practices
- [File Naming Guidelines by ELIXIR Belgium](https://rdm.elixir-belgium.org/file_naming)
- [Folder Structure Recommendations by ELIXIR Belgium](https://rdm.elixir-belgium.org/folder_structure)
- [NFDI4Plants Data Plan Tool](https://www.nfdi4plants.de/dataplan/)

For more details, consult the full [Knowledge Base on RDM](https://knowledgebase.nfdi4microbiota.de/Research-Data-Management/01-introduction.html).
