# In Silico Annotation & ACMG Evidence Curation of *MYOD1* Missense Variants of Uncertain Significance in Rhabdomyosarcoma
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21929026.svg)](https://doi.org/10.5281/zenodo.21929026)

## Executive Summary
Variants of Uncertain Significance (VUS) present a critical challenge in clinical genetics and cancer predisposition screening. *MYOD1* is a master regulator bHLH transcription factor critical for skeletal muscle differentiation and frequently altered in pediatric embryonal Rhabdomyosarcoma (eRMS). 

This project applies a systematic bioinformatics pipeline integrating **ClinVar**, **gnomAD v4**, and ensemble pathogenicity meta-predictors (**REVEL**, **CADD**, **AlphaMissense**) to curate computational evidence for **54 missense VUS entries** in *MYOD1* according to **ACMG/AMP guidelines**.

---

## Methodology Pipeline
1. **Variant Extraction:** Downloaded all 54 germline missense VUS entries for *MYOD1* (transcript `NM_002478.5` / `ENST00000250003.4`) from NCBI ClinVar.
2. **Annotation & Predictor Scoring:** Batch-processed variants through Ensembl VEP to retrieve:
   - Population Allele Frequencies (**gnomAD exomes v4**)
   - Ensemble Pathogenicity Predictors (**REVEL**, **CADD PHRED**, **AlphaMissense**)
   - Standard reference scores (**SIFT**, **PolyPhen-2**)
3. **ACMG Criteria Assignment:** Assigned standardized evidence codes based on established cutoff criteria:
   - **`PP3` (Supporting Pathogenic):** REVEL ≥ 0.75, CADD ≥ 25.0, AlphaMissense = *likely_pathogenic*.
   - **`BP4` (Supporting Benign):** REVEL < 0.50, AlphaMissense = *likely_benign*.
   - **`PM2` (Supporting Pathogenic):** gnomAD Global AF = 0 or < 0.000015.

---

## Key Findings & Results
- **31 / 54 Variants (57.4%) Lean Benign (`BP4, PM2`):** Exhibited low REVEL scores (< 0.50) and benign AlphaMissense predictions, suggesting minimal impact on protein function.
- **7 / 54 Variants (13.0%) Lean Pathogenic (`PP3, PM2`):** Exhibited strong, unanimous computational pathogenicity across REVEL (≥ 0.75), CADD (≥ 26), and AlphaMissense:
  - `p.Asp39Gly` (`c.116A>G`) — REVEL: 0.751, CADD: 31.0
  - `p.Ala83Glu` (`c.248C>A`) — REVEL: 0.800, CADD: 33.0
  - `p.Cys93Tyr` (`c.278G>A`) — REVEL: 0.936, CADD: 34.0
  - `p.Asp109Glu` (`c.327C>A`) — REVEL: 0.755, CADD: 26.3
  - `p.Ile157Val` (`c.469A>G`) — REVEL: 0.912, CADD: 28.1
  - `p.Ser197Phe` (`c.590C>T`) — REVEL: 0.777, CADD: 29.7
  - `p.Ser204Cys` (`c.611C>G`) — REVEL: 0.829, CADD: 33.0

---

## Visualizations
![Predictor Concordance](myod1_vus_analysis.png)
*Figure 1: REVEL vs. CADD PHRED scores for MYOD1 missense VUS categorized by AlphaMissense predictions.*

![ACMG Distribution](acmg_code_distribution.png)
*Figure 2: Distribution of ACMG evidence code combinations across 54 curated MYOD1 variants.*

---

## Repository Structure
- `MYOD1_VUS_Master_Curation.xlsx`: Fully annotated Master Table containing ClinVar IDs, gnomAD frequencies, VEP scores, and ACMG codes.
- `myod1_vus_analysis.png`: Scatter plot visualization.
- `acmg_code_distribution.png`: ACMG classification bar chart.

---

## Author
- Shravani | Manipal Institute of Regenerative Medicine (MIRM)
- Focus: Regenerative Medicine, Stem Cell Research & Computational Genomics
