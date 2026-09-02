# Tcell_single_cell_immunometabolic_profiling

Protein synthesis-based single-cell metabolic profiling of T cells using high-dimensional flow cytometry — Moraly et al., *Nature Immunology* manuscript, 2026.

<p align="center">
  <img width="2231" height="513" alt="Single-cell immunometabolic profiling" src="https://github.com/user-attachments/assets/d70e068c-2e1a-4150-b71f-6f5903c66e20" />
</p>

## Overview

This repository contains the analysis pipeline for protein synthesis-based single-cell immunometabolic profiling of T cells.

The approach uses short-pulse puromycin incorporation as a single-cell readout of protein synthesis and high-dimensional flow cytometry to quantify metabolic activity and pathway dependencies across T-cell populations.

## Repository contents

* [`data/`](data/) — example healthy-donor CD3+ T-cell dataset obtained from freshly isolated human PBMCs
* [`code/`](code/) — Jupyter notebook for data processing, calculation of metabolic dependencies, PARC clustering, and UMAP visualization.

```text
Tcell_single_cell_immunometabolic_profiling/
├── README.md
├── data/
│   └── example healthy-donor FCS files
└── code/
    └── single_cell_immunometabolic_profiling.ipynb
```

## Analysis workflow

The pipeline includes:

1. Import and concatenation of FCS files and associated sample metadata.
2. Transformation and normalization of flow cytometry marker intensities.
3. Calculation of protein synthesis and metabolic pathway dependencies from puromycin incorporation.
4. High-dimensional clustering of T-cell populations using PARC.
5. UMAP visualization of PARC clusters and associated metabolic and phenotypic features.

## Example data

The included healthy-donor PBMC dataset is provided to demonstrate the analysis workflow and enable users to run the pipeline.

