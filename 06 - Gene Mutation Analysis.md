# Gene Mutation Analysis
  - This document summarizes the complete workflow I performed for colon cancer gene mutation analysis using the **cBioPortal (TCGA‑GDC COAD dataset)**.
  - Mutation information was collected for key colorectal cancer–associated genes such as **APC, KRAS, TP53, SMAD4, MLH1, MSH2, and MSH6**.
  - The following steps describe how mutation data was downloaded, relevant transcripts selected, reference sequences retrieved, mutations manually incorporated, mutated protein sequences translated, and the functional impact of each variant assessed.
    
## 1.Data Collection:
  - I Used cBioPortal (TCGA-GDC COAD dataset) to view and explore mutation information for colon cancer related genes.
  - I obtained relevant details including gene name, mutation type, HGVS notation, affected transcripts.
  - I Verified that transcript IDs in NCBI RefSeq (NM_ for mRNA, NP_ for protein) to ensure accuracy in sequence retrieval and mutation analysis.
    
## 2.Selecting Gene and Transcripts
  - I chosed major colon cancer–related genes: *APC, KRAS, TP53, SMAD4, MLH1, MSH2, MSH6*.
  - For each gene, I identified and verified the main transcript (NM_) in NCBI RefSeq, ensuring it matched cBioPortal’s dataset.
  - I retrieved the corresponding NP_ protein accession for each transcript.
  - I cross-checked the amino acid length in cBioPortal to make sure NM_ and NP_ IDs belonged to the same transcript version.
  - After verification, I finalized the transcript IDs for mutation analysis.
    
## 3.Downloading Reference Nucleotide and Protein Sequence (FASTA)
  - For each gene, I searched the NCBI database.
  - I selected the reference sequence record (NM_) exactly matching the transcript used in cBioPortal.
  - I downloaded both the reference nucleotide (NM_) and protein (NP_) sequences in FASTA format.
  - I saved these with clear filenames for individual genes (e.g., APC-Nucleotide-Normal.fasta, APC-Protein-Normal.fasta).
    
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
  - I retrieved UniProt IDs and Pfam domains, confirming mutation locations inside conserved or functionally key regions.
  -  Finaly, I selected specific mutations for analysis (E.g: APC R876*, KRAS G12C, TP53 Y220C, SMAD4 R361C, MLH1 G67R, MSH2 T806Kfs*4, MSH6 E1322*, PMS2 R211**).

## 6.Incorporating Mutation Changes into the Nucleotide Sequence
  - I manually opened each reference nucleotide FASTA in VS Code and edited the sequence for each gene’s mutations..
  - I used the *HGVSg notation* to locate the exact nucleotide position that needed modification. 
  - Different types of gene mutations require different sequence changes.
     ### In this analysis, I worked with three mutation types:
      - Missense mutations : Replaced a single nucleotide (E.g: C → T).
      - Nonsense mutations : Modified the codon to introduce a premature stop codon (E.g: Changing a codon into TGA/TAA/TAG).
      - Frameshift mutations : Added or Deleted the exact nucleotides as specified in the *HGVSc* description
        
  - I Saved each mutated FASTA files separately for comparison with the refereance sequence.

## 7.Translating Nucleotide Sequence to Protein Sequence
  - Since I already had the reference protein sequence (NP_), I focused on translating the mutated nucleotide FASTA sequence.
  - I used the online tranlation tool( ExPASy Translate tool) for  verifying the correct reading frame started at the ATG codon.
  - I confirmed that the translated sequence reflected the anticipated amino acid change.
  - I saved the mutated protein FASTA for sequence alignment.
     
## 8.Identifying the Amino Acid Change
  - I imported both the reference and the mutated protein sequence as well as referance and mutated nucleotide sequences into MEGA software for alignment and comparison.
  - I Aligned the sequences to visually identify the exact amino acid position affected by the mutation.
    ### Observed whether the mutation resulted in:
     - Missense change (one amino acid replaced by another)
     - Nonsense change (amino acid replaced by a stop codon *)
     - Frameshift effect (downstream amino acids shifted and altered)
  - Saved the MEGA alignment files separately for protein and nucleotide sequences.
  - Verified that the nucleotide changes observed in MEGA matched the HGVS nucleotide notation reported in cBioPortal.
  - Verified that the amino acid change identified in MEGA matched the HGVS protein notation from cBioPortal.

## 9.Predicting Functional Changes
  - For each mutation, I noted the predicted functional effects by checking the mutation type, Pfam domain overlap, and the amino acid changes seen in MEGA.
  - I used this information to interpret the functional significance of these mutations.
    
## 10.Summary
  I documented every step in analyzing colon cancer gene mutations: obtaining details from cBioPortal, verifying transcript identities through NCBI, manually introducing mutations into sequences, translating and aligning in MEGA, and evaluating impacts through UniProt/Pfam to clearly interpret the biological consequences of each variant
  
## Gene Mutation Information


| S.No|Gene Name|Gene ID|Ref Transcript Id|Ref Protein ID|Uniprot ID|Pfam ID|Protein change|Amino Acid change|Mutation type|Nucleotide position and change|SNP ID      |PDB ID|
|-----|---------|-------|-----------------|--------------|----------|-------|--------------|-----------------|-------------|------------------------------|------------|------|
| 1   |  APC    | 324   | NM_000029.2     | NP_000029.2  | P25054   |PF16629|  R876*       |  p.Arg876*      | Nonsense    |   c.2626C>T                  |rs121913333 |3T7U  |
| 2   |  KRAS   | 3845  | NM_004985.5     | NP_004976.2  | Q07983   |PF00071|  G12C        |  p.Gly12Cys     | Missence    |    c.34G>T                   |rs121913530 |6OI3  |
| 3   |  TP53   | 7157  | NM_000546.6     | NP_000537.3  | P04637   |PF00870|  Y220C       |  p.Tyr220Cys    | Missence    |    c.659A>G                  |rs121912666 |1GZH  |
| 4   |  SMAD4  | 4089  | NM_005359.6     | NP_005350.1  | Q13485   |PF03166|  R361C       |  p.Arg361Cys    | Missence    |    c.1081C>T                 |rs80338963  |1DD1  |    
| 5   |  MLH1   | 4292  | NM_000249.4     | NP_000240.1  | P43246   |PF13589|  G67R        |  p.Gly67Arg     | Missence    |    c.199G>A                  |rs63750206  |4PLA  |
| 6   |  MSH2   | 4436  | NM_000251.3     | NP_000242.1  | P43246   |PF00488|  T806Kfs*4   | p.Thr806Lysfs*4 | Frame shift |    c.2415_2421del            |            |2O8B  |                                               |  7  |  MSH6   | 2956  | NM_000179       | NP_000170.1  | P52701   |PF00488| E1322*       |  p.Glu1322*     | Nonsense    |    c.3964G>T                 |rs1553333707|2O8B  |                                               | 8   |  PMS2   | 5395  | NM_000526.2     | NP_000526.2  | P54278   |PF01119|  R211*       |  p.Arg211*      | Nonsense    |    c.631C>T                  |rs760228510 |1EA6  |                         

### Database and Tools used 
- cBioPortal(TCGA-GDC-COAD)
- NCBI RefSeq
- UniProt
- Pfam
- ExPASy Translate
- MEGA
