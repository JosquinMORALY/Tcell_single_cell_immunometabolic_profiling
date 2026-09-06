# Tcell_single_cell_immunometabolic_profiling

Protein synthesis-based single-cell metabolic profiling of T cells using high-dimensional flow cytometry — Moraly et al., *Nature Immunology* manuscript, 2026.

<p align="center">
  <img width="2231" height="513" alt="Single-cell immunometabolic profiling" src="https://github.com/user-attachments/assets/d70e068c-2e1a-4150-b71f-6f5903c66e20" />
</p>

## Overview

This repository contains the analysis pipeline for protein synthesis-based single-cell immunometabolic profiling of T cells.

The approach uses short-pulse puromycin incorporation as a single-cell readout of protein synthesis and metabolic dependencies. Cells are analyzed under four conditions: DMSO (vehicle control), OLIGO (oligomycin; ATP synthase inhibition), CHX (cycloheximide; protein synthesis inhibition), and NP (no puromycin control). Metabolic dependencies are calculated as described in the SCENITH framework by Argüello et al. [1]. High-dimensional flow cytometry enables these metabolic parameters to be resolved across phenotypically defined T-cell populations.

## Repository contents

* [`data/`](data/) — example healthy-donor CD3+ T-cell dataset obtained from freshly isolated human PBMCs
* [`code/`](code/) — Jupyter notebook for data processing, calculation of metabolic dependencies, PARC clustering, and UMAP visualization

```text
Tcell_single_cell_immunometabolic_profiling/
├── README.md
├── LICENSE
├── requirements.txt
├── data/
│   └── example healthy-donor FCS files
└── code/
    └── single_cell_immunometabolic_profiling.ipynb
```

## Analysis workflow

The pipeline includes:

1. Import and concatenation of FCS files and associated sample metadata.
2. Transformation and normalization of flow cytometry marker intensities.
3. High-dimensional clustering of T-cell populations using PARC [2], based on phenotypic markers and excluding puromycin from clustering.
4. Calculation of protein synthesis and OXPHOS dependence from puromycin incorporation within each PARC-defined cluster.
5. UMAP visualization of PARC clusters and associated metabolic and phenotypic features.

## System requirements

The analysis notebook was tested locally using Jupyter with **Python 3.12.2**.

The following Python packages were used:

* NumPy 1.26.4
* pandas 2.2.3
* Matplotlib 3.9.2
* seaborn 0.13.2
* SciPy 1.17.1
* scikit-learn 1.5.1
* FlowCytometryTools 0.5.1
* fcsparser 0.2.8
* PARC 0.40
* hnswlib 0.8.0
* umap-learn 0.5.7

Package dependencies and versions are also provided in [`requirements.txt`](requirements.txt).

No non-standard hardware is required.

## Installation

Clone the repository and install the required Python dependencies:

```bash
git clone https://github.com/JosquinMORALY/Tcell_single_cell_immunometabolic_profiling.git
cd Tcell_single_cell_immunometabolic_profiling
pip install -r requirements.txt
```

Installation of the required packages typically takes a few minutes on a standard desktop computer.

## Demo and instructions for use

The example healthy-donor PBMC dataset provided in the [`data/`](data/) directory can be used to run the complete analysis workflow.

Open:

```text
code/single_cell_immunometabolic_profiling.ipynb
```

and run the notebook sequentially from top to bottom.

The notebook performs FCS import and preprocessing, calculation of protein synthesis and metabolic dependencies, PARC clustering, and UMAP-based visualization.

**Expected output:** processed single-cell data, PARC cluster assignments, metabolic dependency measurements, and UMAP visualizations of metabolic and phenotypic features.

The notebook can also be applied to other datasets provided that the input FCS files and associated metadata follow the same structure as the example dataset.

## Example data

The included healthy-donor PBMC dataset is provided to demonstrate the analysis workflow and enable users to run the pipeline.

## Reproducing manuscript analyses

The notebook provides the analysis workflow used for the single-cell immunometabolic profiling analyses described in the corresponding manuscript.

## Data availability

The example dataset required to run the analysis workflow is provided in the [`data/`](data/) directory.

## License

The code in this repository is available under the [MIT License](LICENSE).

## References

1. Argüello RJ, Combes AJ, Char R, et al. SCENITH: A Flow Cytometry-Based Method to Functionally Profile Energy Metabolism with Single-Cell Resolution. *Cell Metabolism*. 2020. DOI: 10.1016/j.cmet.2020.11.007.

2. Stassen SV, Siu DMD, Lee KCM, et al. PARC: ultrafast and accurate clustering of phenotypic data of millions of single cells. *Bioinformatics*. 2020;36(9):2778–2786. DOI: 10.1093/bioinformatics/btaa042.
