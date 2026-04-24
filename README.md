# Evaluating Protein Language Models ESM2 for Mutation Based Survival Prediction in Glioma

Diffuse glioma survival is strongly influenced by recurrent driver mutations and molecular subtype. In this project, I compared two ways of representing somatic mutation data for patient-level survival analysis:

1. **Binary mutation encoding**  
   Each gene was coded as mutated or wild type for each patient.

2. **ESM2-derived features**  
   Missense mutations were represented using attention-weighted features derived from the ESM2 protein language model.

The main aim was to test whether sequence-informed mutation features provide additional prognostic value beyond simple gene-level mutation status.

## Main objectives

- Retrieve and harmonize TCGA glioma mutation and clinical data
- Construct binary mutation features and ESM2-derived mutation features
- Perform univariate Cox regression to identify survival-associated genes
- Compare predictive performance using Elastic Net Cox and Random Survival Forest models
- Examine the biological properties of ESM2-derived attention scores at the residue level

