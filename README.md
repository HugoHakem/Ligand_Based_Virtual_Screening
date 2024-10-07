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
1. Gimeno, Aleix, et al. "The Light and Dark Sides of Virtual Screening: What Is There to Know?" International Journal of Molecular Sciences, vol. 20, no. 6, March 2019, p. 1375. DOI.
2. Rohrer, Sebastian G., and Knut Baumann. "Maximum Unbiased Validation (MUV) Data Sets for Virtual Screening Based on PubChem
Bioactivity Data." Journal of Chemical Information and Modeling, vol. 49, no. 2, Feb. 2009, pp. 169–184. DOI.
3. Xia, Jie, et al. "Benchmarking methods and data sets for ligand enrichment assessment in virtual screening." Methods, vol. 71, Jan. 2015, pp. 146–157. DOI.
4. MoleculeNet: Datasets.
5. "How to explain the ROC AUC score and ROC curve?" Evidently AI, consulted 25 April 2024. Link.
6. "6.1: Molecular Descriptors". Chemistry LibreTexts, 26 Oct. 2019. Link.
7. Li, J., Cai, D., and He, X. "Learning Graph-Level Representation for Drug Discovery." arXiv, 15 Sept. 2017. Link.
8. Wang, C., Deng, C., and Wang, S. "Imbalance-XGBoost: Leveraging Weighted and Focal Losses for Binary Label-Imbalanced
9. Classification with XGBoost." 2019.
"Introduction to Scaffold Splitting". Oloren AI, consulted 25 April 2024. Link.
10. Hu, W. et al., "Open Graph Benchmark: Datasets for Machine Learning on Graphs", arXiv preprint arXiv:2005.00687, 2020.
11. Li, P. et al., "TrimNet: learning molecular representation from triplet messages for biomedicine", Briefings in Bioinformatics, Nov. 2020, DOI.
