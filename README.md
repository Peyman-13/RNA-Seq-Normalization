
# Modern RNA-Seq Normalization & Quality Control 🧬📊

## Overview
This repository contains a comprehensive pipeline in R demonstrating modern normalization and quality control techniques for bulk RNA-Sequencing data. It serves as a practical guide to handling the mean-variance relationship inherent in transcriptomic data, transitioning away from legacy microarray methods to modern count-based standards.

## The Dataset
This pipeline uses the `airway` dataset from Bioconductor, which features bulk RNA-Seq read counts from airway smooth muscle cells treated with dexamethasone versus untreated controls.

## Methods Explored
This document walks through the mathematical rationale, implementation, and visualization of the following preprocessing steps:
* **Raw Data Visualization:** Density and MA plots highlighting sequencing depth biases.
* **CPM & TPM:** Correcting for library size and transcript length.
* **TMM (`edgeR`):** Trimmed Mean of M-values for robust scaling.
* **Median of Ratios (`DESeq2`):** Erasing systematic technical biases for differential expression.
* **Variance Stabilizing Transformation (VST):** Squashing the mean-variance relationship for downstream machine learning.
* **limma-voom:** Transforming count data for linear modeling.
* **Quality Control:** Principal Component Analysis (PCA), Sample-to-Sample Euclidean Distance Heatmaps, and Dispersion Estimates.

## How to Run
To compile the R Markdown document locally, ensure you have R installed along with the following Bioconductor packages:
`airway`, `edgeR`, `DESeq2`, `limma`, `preprocessCore`, `RColorBrewer`, and `pheatmap`.

```R
# Install dependencies
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install(c("airway", "edgeR", "DESeq2", "limma", "preprocessCore"))

