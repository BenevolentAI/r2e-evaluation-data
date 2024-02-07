# Retrieve to Explain (R2E) Evaluation Data

This repository contains the three performance evaluation datasets associated with our paper: [*Retrieve to Explain: Evidence-driven Predictions with Language Models*](https://arxiv.org/abs/2402.04068).

Authors: Ravi Patel, Angus Brayne, Rogier Hintzen, Daniel Jaroslawicz, Georgiana Neculae, Dane Corneil

All datasets are in TSV format, with the first row being the header. Please refer to the paper for full descriptions of each of the datasets and how they were constructed.

## Datasets

### *Held-out Biomedical Literature* Test dataset

File: `datasets/heldout_biomedical_literature_test.tsv`

Fields:
- `gene_name`: The gene entity to predict (assigned with the Ensembl "name" field if available, otherwise HGNC "symbol")
- `query`: Abstract-section scientific literature sentence with mentions of the gene in `gene_name` masked out with `[MASK]`
- `pubmed_id`: PubMed ID of the source document for the sentence
- `publication_year`: Year of publication of the source document (2020, 2021, 2022)

License: *Held-out Biomedical Literature* Test is adapted from literature sentences courtesy of the National Library of Medicine.

### *Held-out Biomedical Literature* Validation dataset 

File: `datasets/heldout_biomedical_literature_validation.tsv`

Fields:
- `gene_name`: The gene entity to predict (assigned with the Ensembl "name" field if available, otherwise HGNC "symbol")
- `query`: Abstract-section scientific literature sentence (published 2020 onwards) with mentions of the gene in `gene_name` masked out with `[MASK]`
- `pubmed_id`: PubMed ID of the source document for the sentence

License: *Held-out Biomedical Literature* Validation is adapted from literature sentences courtesy of the National Library of Medicine.

### *Gene Description Facts* dataset

File: `datasets/gene_description_facts.tsv`

Fields:
- `gene_name`: The gene entity to predict (assigned with the Ensembl "name" field if available, otherwise HGNC "symbol")
- `query`: Fact adapted from a UniProt Gene description, with mentions of the gene in `gene_name` masked out with `[MASK]`

License: *Gene Description Facts* © 2024 by [BenevolentAI](https://www.benevolent.com/) is licensed under [CC BY-NC-SA 4.0](http://creativecommons.org/licenses/by-nc-sa/4.0/). It is adapted from "Universal Protein Resource (UniProt)" by Uniprot Consortium, used under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

### *Clinical Trial Outcomes* dataset

File: `datasets/clinical_trial_outcomes.tsv`

Fields:
- `gene_name`: The gene entity to predict (assigned with the Ensembl "name" field if available, otherwise HGNC "symbol")
- `query`: Clinical trial outcome query containing both `[MASK]` and the clinical trial indication meshName from the `indication_meshName` field
- `indication_meshId`: Clinical trial indication (disease) meshId
- `indication_meshName`: Clinical trial indication (disease) meshName
- `clinical_success`: Whether for the specified Gene and indication, there was successful progression from clinical trial phase II/III to regulatory approval (1 = success, 0 = failure)

License: *Clinical Trials Outcomes* © 2024 by [BenevolentAI](https://www.benevolent.com/) is licensed under [CC BY-NC-SA 4.0](http://creativecommons.org/licenses/by-nc-sa/4.0/). We have permission from Citeline PharmaProjects to publicly release the subset of their data that appear here.