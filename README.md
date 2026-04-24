# Glioma survival modelling with binary mutation encoding and ESM2-derived features

This repository contains the code and supporting analysis files for a dissertation project comparing conventional binary mutation encoding with ESM2-derived protein language model features for survival modelling in TCGA glioma cohorts.

## Project summary

Diffuse glioma survival is strongly influenced by recurrent driver mutations and molecular subtype. In this project, I compared two ways of representing somatic mutation data for patient-level survival analysis:

1. **Binary mutation encoding**  
   Each gene was coded as mutated or wild type for each patient.

2. **ESM2-derived features**  
   Missense mutations were represented using attention-weighted features derived from the ESM2 protein language model through the ProtEncode framework.

The main aim was to assess whether sequence-informed mutation features provide additional prognostic value beyond simple gene-level mutation status.

## Main objectives

- retrieve and harmonize TCGA glioma mutation and clinical data
- construct binary mutation features and ESM2-derived mutation features
- perform univariate Cox regression to identify survival-associated genes
- compare predictive performance using Elastic Net Cox and Random Survival Forest models
- examine the biological properties of ESM2-derived attention scores at the residue level

## Repository structure

.
├── README.md
├── LICENSE
├── CITATION.cff
├── scripts/
├── figures/
├── results/
├── data/
└── docs/

### Suggested folder contents

- `scripts/`  
  Analysis scripts for data processing, feature construction, survival analysis, modelling, and figure generation.

- `figures/`  
  Final figures used in the dissertation and any reproducible figure output.

- `results/`  
  Summary tables, model outputs, and processed result files.

- `data/`  
  Notes on data sources and retrieval.  
  Raw protected or restricted data should **not** be uploaded directly unless redistribution is explicitly permitted.

- `docs/`  
  Optional project notes, workflow diagrams, and supplementary documentation.

## Data sources

This project uses publicly available data from:

- **The Cancer Genome Atlas (TCGA)** for glioma mutation and clinical data
- **Genomic Data Commons (GDC)** portal for data access
- **UniProt Swiss-Prot** for canonical human protein sequences

Where raw data cannot be redistributed directly, scripts are provided to reproduce data retrieval and preprocessing from the original public sources.

## Methods overview

The main analysis steps were:

1. download and merge TCGA-GBM and TCGA-LGG mutation and clinical data
2. derive patient-level overall survival information
3. construct binary mutation features from non-silent somatic mutations
4. generate mutant protein sequences from missense variants
5. encode mutant sequences using the ESM2 model through the ProtEncode framework
6. build a unified analysis dataset with matched genes and samples
7. run univariate Cox regression for binary and ESM2-derived features
8. evaluate predictive performance using:
   - Elastic Net Cox regression
   - Random Survival Forests
   - 5-fold cross-validation
9. analyse residue-level score patterns in selected genes

## Reproducibility

To reproduce the analysis:

1. clone this repository
2. install the required software and dependencies
3. retrieve the source data from the public databases listed above
4. run the scripts in the intended order

## Software and dependencies

This project was conducted primarily in:

R [4.5.1]

## Main packages/frameworks include:

TCGAbiolinks
survival
glmnet
randomForestSRC
tidyverse
ESM2
ProtEncode

## Acknowledgement

This repository accompanies a dissertation project completed at [UoE /Biomedical and health applications of data science].
I would like to thank Mr Christopher Oldnall for his supervision and support throughout the project.

## Contact

For questions about this repository, please contact:

Zhen Xiao — [tessie0929@163.com]

## License

This project is licensed under the terms of the MIT License
.
