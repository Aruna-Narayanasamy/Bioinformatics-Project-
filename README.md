# Drug–Target Interaction Prediction for Colon Cancer Using Deep Learning

 - A multi-stage computational project integrating gene mutation analysis, variant annotation, and protein structure interpretation as a biological foundation for deep learning–based drug–target interaction prediction in colon cancer.

---

## Introduction

Colon cancer (colorectal cancer) is one of the most common and deadly cancers worldwide. It arises due to the accumulation of genetic alterations that disrupt key signaling pathways controlling cell growth, differentiation, and genome stability. Although multiple therapeutic options exist, challenges such as drug resistance, limited response rates, and adverse side effects highlight the need for improved treatment strategies.

Computational approaches play an increasingly important role in modern drug discovery by enabling large-scale analysis of genomic, structural, and molecular data. In particular, Drug–Target Interaction (DTI) prediction methods can help identify potential therapeutic targets and candidate drugs in a faster and more cost-effective manner.

This project aims to support colon cancer drug discovery by building a biologically informed computational pipeline, beginning with mutation analysis and protein structure interpretation and extending toward deep learning–based DTI prediction.

---

## Objectives

The main objective of this project is to develop a computational framework to predict Drug–Target Interactions (DTIs) relevant to colon cancer.

### Specific Objectives
- Identify key genes and mutations involved in colon cancer progression
- Perform functional annotation of genetic variants using standardized tools
- Interpret the structural consequences of high-impact mutations
- Establish biologically meaningful protein targets for downstream analysis
- Create a foundation for future deep learning–based DTI prediction models

---

## Project Scope and Current Status

This project is designed as a **multi-stage computational pipeline** for colon cancer research.

### Current Scope (Completed)

The current implementation focuses on building a **strong biological and structural foundation**, which is essential before applying any deep learning or predictive modeling approaches. Completed work includes:

- Collection of colon cancer mutation data from **cBioPortal (TCGA-GDC COAD dataset)**
- Manual curation and verification of transcripts using **NCBI RefSeq**
- Functional annotation of variants using the **Ensembl Variant Effect Predictor (VEP)**
- Prioritization of biologically significant mutations based on impact and domain context
- Protein structure analysis of selected high-impact genes:
  - **APC**: Structural interpretation of truncation caused by the R876* nonsense mutation
  - **KRAS**: Structural comparison of wild-type and G12C mutant proteins
- Visualization and interpretation of mutation-induced structural changes using **PyMOL** 

These steps ensure that selected targets and mutations are biologically meaningful and structurally interpretable.

### Planned Extension (Future Work)

Future stages of the project will include:
- Integration of curated drug and protein datasets
- Feature extraction from molecular and sequence data
- Development of deep learning models for DTI prediction
- Biological interpretation of predicted interactions

---

## Repository Structure
|---01 - Drug-Target Interaction prediction for Colon Cancer using Deep Learning.md

|---02 - Introduction and Objective.md

|---03 - Colon Anatomy and Biology.md

|---04 - Colon cancer pathway.md

|---05 - Methodology.md

|---06 - Gene Mutation Analysis.md

|---07 - Protein Structural Analysis.md

|---08 - APC_Structural_Analysis.md

|---09 - KRAS_Structural_Analysis.md




## Workflow Overview

**High-Level Computational Workflow**

1. Colon cancer gene selection  
2. Mutation data collection (TCGA via cBioPortal)  
3. Transcript verification (NCBI RefSeq)  
4. Variant annotation (Ensembl VEP)  
5. Mutation prioritization  
6. Protein structure modeling and visualization  
7. Structural interpretation of mutation effects  
8. (Planned) Deep learning–based DTI prediction  

---

## Documentation

Detailed documentation for each stage is provided below:

- **Gene Mutation Analysis**  
  `06 - Gene Mutation Analysis.md`

- **Variant Annotation (VEP)**  
  `VEP_Annotation.md`

- **Structural Analysis of APC**  
  `APC_Structural_Analysis.md`

- **Structural Analysis of KRAS**  
  `KRAS_Structural_Analysis.md`

---

## Tools and Databases Used

### Databases
- cBioPortal (TCGA-GDC COAD)
- NCBI RefSeq
- Ensembl
- UniProt
- Pfam
- Protein Data Bank (PDB)

### Software and Tools
- Ensembl Variant Effect Predictor (VEP)
- PyMOL Molecular Graphics System
- SWISS-MODEL
- MEGA (sequence alignment)

---

## References

- The Cancer Genome Atlas (TCGA)
- Ensembl Variant Effect Predictor documentation
- Protein Data Bank
- SWISS-MODEL documentation

