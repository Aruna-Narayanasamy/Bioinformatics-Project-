# Project Overview
## Introduction

Colon cancer (colorectal cancer) is one of the most prevalent and life-threatening cancers worldwide.  
Its progression is driven by the accumulation of genetic alterations that disrupt key cellular pathways involved in cell growth, differentiation, and genome stability.

Although multiple treatment options exist, challenges such as drug resistance, variable patient response, and adverse side effects highlight the need for improved therapeutic strategies.  
Computational approaches offer a cost-effective and scalable way to analyze large biological datasets and support drug discovery.

This project adopts a computational (in silico) strategy to study colon cancer at the **genomic and structural levels**, with the long-term goal of supporting **Drug–Target Interaction (DTI) prediction using deep learning**.

---

## Objectives

The primary objective of this project is to establish a biologically meaningful computational framework for colon cancer drug discovery.

### Specific Objectives

- Identify key genes involved in colon cancer progression
- Analyze clinically relevant mutations using public cancer genomics datasets
- Perform functional annotation of variants using standardized tools
- Interpret mutation effects at the protein structure level
- Prioritize biologically relevant targets for downstream analysis
- Establish a foundation for future deep learning–based DTI prediction

---

## Overall Workflow

This project follows a **stepwise and modular workflow**, ensuring biological relevance before applying predictive modeling techniques.

### Workflow Steps

1. **Gene Selection**
   - Identification of key colon cancer–associated genes based on literature and cancer genomics data

2. **Mutation Data Collection**
   - Retrieval of mutation data from cBioPortal (TCGA-GDC COAD dataset)

3. **Transcript Verification**
   - Verification of reference transcripts using NCBI RefSeq (NM_ / NP_ accessions)

4. **Variant Annotation**
   - Functional annotation of variants using Ensembl Variant Effect Predictor (VEP)
   - Classification of variants by consequence and predicted impact

5. **Mutation Prioritization**
   - Selection of high-impact and biologically significant mutations
   - Consideration of domain location and functional relevance

6. **Protein Structure Analysis**
   - Structural interpretation of selected mutations
   - APC analyzed for truncation effects
   - KRAS analyzed for local mutation-induced structural changes

7. **Future Extension (Planned)**
   - Integration of drug data
   - Feature extraction for proteins and compounds
   - Deep learning–based Drug–Target Interaction prediction

---

## Scope of the Current Work

The current implementation focuses on **mutation analysis, variant annotation, and protein structure interpretation**.  
These steps provide the biological and mechanistic foundation required before applying machine learning or deep learning approaches.

Detailed analyses for each stage are provided in separate documentation files linked from the main README.
