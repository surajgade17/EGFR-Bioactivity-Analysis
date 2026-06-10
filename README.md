# EGFR Bioactivity Analysis

## Overview
Analysis of bioactivity data for Epidermal Growth Factor Receptor (EGFR) — 
a key cancer drug target — using real data from the ChEMBL database.

## What is EGFR?
EGFR is a protein overexpressed in many cancers. Drugs like Gefitinib 
and Erlotinib work by blocking it. Finding potent EGFR inhibitors 
is a major focus of cancer drug discovery.

## Dataset
- Source: ChEMBL Database (Target: CHEMBL203)
- 26,600 compounds fetched
- 22,028 compounds after cleaning
- Labels: Active (IC50 ≤ 1000 nM), Inactive (IC50 ≥ 10000 nM)

## What I Did
1. Fetched real bioactivity data from ChEMBL API
2. Cleaned and labeled compounds by IC50 values
3. Calculated Lipinski descriptors using RDKit
4. Visualized bioactivity distribution and drug-likeness

## Key Findings
- 18,384 active compounds identified against EGFR
- Active compounds largely follow Lipinski's Rule of Five
- Clear separation between active/inactive IC50 distributions

## Tools Used
- Python, Pandas, NumPy, Matplotlib
- RDKit, ChEMBL Web Resource Client
- Google Colab (mobile-based development)

## Author
Suraj Gade — BSc Chemistry, SPPU
GitHub: surajgade17
