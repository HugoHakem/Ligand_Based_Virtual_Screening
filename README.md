# Efficacy Comparison of Descriptor Modeling and Graph Modeling for Ligand Based Virtual Screening

## Author
Hugo Hakem, MEng BioE '23-24

## Acknowledgements
This project is the final work for the Chem/BioE242 class taught in Spring 2024 by **Professor Teresa Head-Gordon** and **GSI Yingze (Eric) Wang**.

## Background and Motivation
Virtual Screening (VS) is a widely-used method in drug discovery, employed by big pharmaceutical companies to extract a small, focused subset of active compounds from a large virtual database. These active compounds are related to a specific biological target, often a disease-associated protein. The goal is to enrich the fraction of active compounds, accelerating biological testing [1].

Ligand-Based Virtual Screening (LBVS) assumes that active compounds are structurally or chemically similar to known active compounds (ligands), which bind to the desired target [2][3].

This project investigates whether it is more efficient to model compounds using **chemical descriptors** or **graph representations** in relation to bioactivity classification for a specific target.

## Dataset
The dataset used is the **MUV Dataset** from the MoleculeNet database [4]. The MUV dataset, the first benchmarking dataset for LBVS, addresses two critical biases:
- **Artificial Enrichment Bias**: When inactive compounds are too different from active ones.
- **Analogue Bias**: When active compounds are too similar to each other.

The dataset's compounds were characterized using simple descriptors such as the number of atoms, heavy atoms, certain element counts (B, Br, C, Cl, etc.), hydrogen bond acceptors and donors, LogP values, chiral centers, and rings [2]. These descriptors ensure well-scattered compound distribution in the chemical space.

## Project Structure
The project is divided into two main parts, each of which can be run independently:

### I. Descriptor Modeling
- **Dataset**: MUV Dataset
- **Preprocessing**: Descriptor calculation
- **Splitting Method**: Scaffold splitting
- **Model**: XGBoost-based classification
- **Result**: Performance metrics

### II. Graph Modeling
- **Dataset**: MUV Dataset
- **Preprocessing**: Molecular graph representation
- **Splitting Method**: Scaffold splitting
- **Model**: Graph Neural Networks (GNN)
- **Trainer**: PyTorch with PyG
- **Result**: Performance metrics

## Comparison and Conclusion
- Comparison of Descriptor vs. Graph Modeling
- Evaluation against the literature
- General conclusion on the efficacy of each method for bioactivity prediction.

## Installation and Setup
To run the notebook, use the following commands to install the required packages:

```bash
conda install ipykernel conda-forge -y
conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
conda install pyg -c pyg
conda install pandas matplotlib seaborn seaborn rdkit -c conda-forge -y
conda install -c conda-forge py-xgboost
pip install imxgboost
pip install networkx
```

## References
[1] Gimeno, Aleix, et al. « The Light and Dark Sides of Virtual Screening: What Is There to Know? » International Journal of Molecular Sciences, vol. 20, no 6, march 2019, p. 1375. PubMed Central, https://doi.org/10.3390/ijms20061375].
<br>
[2] Rohrer, Sebastian G., et Knut Baumann. « Maximum Unbiased Validation (MUV) Data Sets for Virtual Screening Based on PubChem Bioactivity Data ». Journal of Chemical Information and Modeling, vol. 49, no 2, february 2009, p. 169-84. DOI.org (Crossref), https://doi.org/10.1021/ci8002649.
<br>
[3] Xia, Jie, et al. « Benchmarking methods and data sets for ligand enrichment assessment in virtual screening ». Methods, vol. 71, january 2015, p. 146-57. ScienceDirect, https://doi.org/10.1016/j.ymeth.2014.11.015
<br>
[4] Datasets. https://moleculenet.org/datasets-1. Consulted 4 april 2024.
<br>
[5] « How to explain the ROC AUC score and ROC curve? » Consulté le: 25 avril 2024. [web]. Available: https://www.evidentlyai.com/classification-metrics/explain-roc-curve
<br>
[6] « 6.1: Molecular Descriptors ». Chemistry LibreTexts, 26 october 2019, https://chem.libretexts.org/Courses/Intercollegiate_Courses/Cheminformatics/06%3A_Molecular_Similarity/6.01%3A_Molecular_Descriptors.
<br>
[7] J. Li, D. Cai, et X. He, « Learning Graph-Level Representation for Drug Discovery ». arXiv, 15 septembre 2017. Consulted: 25 april 2024. [Web] Available: http://arxiv.org/abs/1709.03741
<br>
[8] C. Wang, C. Deng, et S. Wang, « Imbalance-XGBoost: Leveraging Weighted and Focal Losses for Binary Label-Imbalanced Classification with XGBoost». 2019.
<br>
[9] « Introduction to Scaffold Splitting - Oloren AI ». Consulted: 25 april 2024. [Web]. Available: https://www.oloren.ai/blog/scaff-split
<br>
[10] W. Hu et al., « Open Graph Benchmark: Datasets for Machine Learning on Graphs », arXiv preprint arXiv:2005.00687, 2020.
<br>
[11] P. Li et al., « TrimNet: learning molecular representation from triplet messages for biomedicine », Briefings in Bioinformatics, nov. 2020, doi: 10.1093/bib/bbaa266.
[12] « Supports Fidle - En ligne ». Cloud UGA, https://cloud.univ-grenoble-alpes.fr/s/wxCztjYBbQ6zwd6. Consulted on April, 27th 2024.
