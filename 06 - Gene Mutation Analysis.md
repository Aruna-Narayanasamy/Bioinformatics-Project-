# Gene Mutation Analysis
  - This document summarizes the complete workflow I performed for colon cancer gene mutation analysis. Using the **cBioPortal (TCGA‑GDC COAD dataset)**.
  -  I collected mutation information for key colorectal cancer–associated genes such as **APC, KRAS, TP53, SMAD4, MLH1, MSH2, and MSH6**.
  -   The steps below describe how I downloaded *mutation data, selected transcripts, extracted reference sequences, manually edited mutations, translated protein sequences, and assessed functional impact of variants*.

## 1.Data Collection:
  - Used cBioPortal (TCGA-GDC COAD dataset) to view and explore mutation information for genes associated with colon cancer.
  - Noted that cBioPortal provides important details such as: Gene name, mutation type, HGVS notation, affected transcripts, and functional impact.
  - Used *NCBI RefSeq* to check and confirm the correct transcript IDs (NM_ and NP_) for each gene, which are required for sequence retrieval and downstream mutation analysis.

## 2.Selecting Gene and Transcripts
  - Selected all key colon cancer–related genes are *APC, KRAS, TP53, SMAD4, MLH1, MSH2, MSH6*.
  - For each selected gene, I identified the major transcript from the NCBI RefSeq database.
  - Ensured that these transcript IDs (NM_) matched the transcript versions reported in cBioPortal (TCGA-GDC COAD).
  - For each NM_ transcript, the corresponding NP_ protein accession was also noted.
  - cBioPortal displays the lenth of amino acids for the selected transcript. It will help to confirm that the nucleotide (NM_) and protein (NP_) sequences belong to the same transcript version.
  - Final transcript IDs were confirmed for downstream sequence retrieval and mutation analysis.
    
## 3.Downloading Reference Nucleotide and Protein Sequence (FASTA)
  - Using the NCBI database, I searched for each colon cancer–related gene.
  - For every gene multiple reference sequence records were available in NCBI.
  - From these, I selected the transcript ID (NM_) that exactly matched the transcript used in cBioPortal (TCGA-GDC COAD) mutation data.
  - After confirming the correct transcript, I downloaded the reference nucleotide sequence and also downloded the corresponding refereence protein sequence for the same transcript.
  - Saved each sequence with clear filenames (E.g: APC-Nucleotide-normal.fasta, APC-Protein-normal.fasta) for further mutation editing and comparison.

## 4.Mutation Data Extraction
  - Downloaded the mutation data (TSV file) for colon cancer (TCGA-GDC COAD) from cBioPortal for each gene.
  - The file contained detailed information about each mutation.
     ### Such as:
      - Gene name
      - HGVS c. (nucleotide change)
      - HGVS p. (protein change)
      - Mutation type (missense, nonsense, frameshift, splice site, etc.)
      - Genomic position
      - Sample ID 

  - Extracted mutation details specifically for the genes of interest: APC, KRAS, TP53, SMAD4, MLH1, MSH2, and MSH6.

## 5.Chossing mutation for analysis
  - From the filtered mutation data, I selected functionally significant mutations for each gene.
    ### Based on:
     - Mutation type (e.g., nonsense, missense, frameshift)
     - Presence in important protein domains (checked using Pfam)

  - cBioPortal also provides visual indicators that highlight the significance of each mutation such as *hotspot or predicted functional impact* and these details were considered while reviewing mutation importance.
  - Using the protein length shown in cBioPortal, I identified the correct *UniProt ID for each protein*.
  - From UniProt, I retrieved the associated *Pfam ID*. In Pfam, I checked for domains whether the mutations occurred within important functional regions.
  -  Finalized specific mutations for detailed downstream analysis (E.g: APC R876*, KRAS G12C, TP53 Y220C, SMAD4 R361C, MLH1 G67R, MSH2 T806Kfs*4, MSH6 E1322*, PMS2 R211**).

## 6.Incorporating Mutation Changes into the Nucleotide Sequence
  - Opened the downloaded reference nucleotide FASTA file in *text editor(VS Code) and manually edited the sequence*. This was done separetly for each gene.
  - Identified the mutation type from cBioPortal.
  - Used the *HGVSg notation* to locate the exact nucleotide position that needed modification. 
  - Different types of gene mutations require different sequence changes.
     ### In this analysis, I worked with three mutation types:
      - Missense mutations : Replaced a single nucleotide (E.g: C → T).
      - Nonsense mutations : Modified the codon to introduce a premature stop codon (E.g: Changing a codon into TGA/TAA/TAG).
      - Frameshift mutations : Added or Deleted the exact nucleotides as specified in the *HGVSc* description
        
  - Saved each mutated FASTA files separately for comparison with the refereance sequence.

## 7.Translating Nucleotide Sequence to Protein Sequence
  - Since the reference protein sequence (NP_) was already downloaded from NCBI in FASTA format. Only the mutated nucleotide FASTA sequence needed translation.
  - I Used an online translation tool (ExPASy Translate) to translate the mutated nucleotide sequence into its corresponding mutated protein sequence.
  - Ensured the correct reading frame was selected based on the start codon (ATG).
  - In Expasy Tranlate tool results Confirmes that the observed amino acid changes matched with the HGVS protein notation (e.g., p.R876*, p.G12C, p.Y220C).
  - Saved the mutated protein sequence as a FASTA file for further alignment in MEGA for comparing the NCBI reference protein sequence with the translated mutated protein sequence to identify the amino acid change.
     
## 8.Identifying the Amino Acid Change
  - The reference and the mutated protein sequence as well as referance and mutated nucleotide sequences imported into MEGA software for alignment and comparison.
  - Aligned the sequences to visually identify the exact amino acid position affected by the mutation.
    ### Observed whether the mutation resulted in:
     - Missense change (one amino acid replaced by another)
     - Nonsense change (amino acid replaced by a stop codon *)
     - Frameshift effect (downstream amino acids shifted and altered)
  - Saved the MEGA alignment files separately for protein and nucleotide sequences.
  - Verified that the nucleotide changes observed in MEGA matched the HGVS nucleotide notation reported in cBioPortal.
  - Verified that the amino acid change identified in MEGA matched the HGVS protein notation from cBioPortal.

## 9.Predicting Functional Changes
  - For each mutation, I noted the functional effect based on the mutation type (missense, nonsense, frameshift).
  - Checked whether the mutation was located inside a functional domain using Pfam information taken earlier.
  - Observed amino acid changes from the MEGA alignment to see if important residues were altered.
  - Based on this information we can predict the fuctional changes.

## 10.Summary
  - This workflow outlines the steps used to analyze colon cancer gene mutations. Mutation details were taken from cBioPortal, and the corresponding reference nucleotide and protein sequences were downloaded from NCBI using the correct transcript IDs.
  - Mutations were manually introduced into the reference nucleotide sequences and the mutated sequences were translated to protein.
  - Both nucleotide and protein sequences were aligned in MEGA to confirm the changes.
  - Functional domains were checked using UniProt/Pfam, and a simple functional impact description was recorded for each mutation. All files were saved, organized, and documented for final reporting.
