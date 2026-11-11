# EGFR Bioactivity Analysis

## Overview
Exploratory analysis of bioactivity data for the Epidermal Growth Factor Receptor (EGFR), a key cancer drug target, using real data from the ChEMBL database.

## What is EGFR?
EGFR is a receptor kinase that is overactive in many cancers. Drugs such as gefitinib and erlotinib block its kinase activity. Finding potent EGFR inhibitors is a major focus of cancer drug discovery.

## Dataset
- **Source:** ChEMBL (target CHEMBL203, human EGFR)
- **Fetched:** 26,600 activity records [CHECK: records or unique compounds]
- **After cleaning:** 22,028 [CHECK: describe filters and duplicate handling, e.g. IC50 only, nM units, "=" relation, duplicates merged by median]
- **Labels:** Active (IC50 <= 1,000 nM), Inactive (IC50 >= 10,000 nM) [CHECK: compounds between 1,000 and 10,000 nM excluded?]

## What I Did
1. Fetched bioactivity data from the ChEMBL API.
2. Cleaned the data and labelled compounds by IC50.
3. Calculated Lipinski descriptors with RDKit.
4. Visualized the bioactivity distribution and drug-likeness in a six-panel dashboard.

![Dashboard](dashboard.png)

## Key Findings
- 18,384 of the 22,028 labelled compounds (83%) are active. The dataset is imbalanced and reflects the published, potent compounds that ChEMBL holds.
- 5,345 compounds are highly potent (pChEMBL >= 8, IC50 <= 10 nM).
- Mean pChEMBL is 7.6 for actives and 4.6 for inactives. This follows from how the labels were defined, so it confirms the labelling rather than being a new result.
- [CHECK: XX% of active compounds break 2 or more Lipinski rules.] This is consistent with known kinase inhibitor chemistry, which often lies outside the Rule of Five.

## Limitations
- Data comes from many labs and assays, so IC50 values are not strictly comparable.
- ChEMBL is biased toward potent, published compounds.
- This is descriptive analysis only; no predictive model has been built yet.

## Next Steps
Scaffold analysis, fingerprint-based similarity, and a QSAR model with scaffold-split validation.

## How to Run
Open the notebook in Google Colab and run the cells in order. It installs RDKit and the ChEMBL web resource client.

## Tools
Python, Pandas, NumPy, Matplotlib, RDKit, ChEMBL Web Resource Client, Google Colab

## Author
Suraj Gade, BSc Chemistry (SPPU), MSc Organic Chemistry student | GitHub: [surajgade17](https://github.com/surajgade17)
