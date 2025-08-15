# Malignant Melanocytes Show Significant Upregulation of Class II Human Leukocytic Antigens

This repository contains the complete analysis workflow and results from an applied field experience project conducted at the University of Maine for **BMS 690: Applied Field Experience**. The project applies **single-cell RNA sequencing (scRNA-seq)** analysis using the **Seurat** R package and **10x Genomics** data to investigate **HLA Class II gene expression** across immune and malignant cell clusters in melanoma.

---

## 📄 Project Overview

**Research Question:**  
Do melanoma cells express Class II Human Leukocytic Antigens (HLA-II), typically restricted to antigen-presenting cells?

**Hypothesis:**  
B-cell clusters will exhibit strong HLA-II upregulation, while melanoma (melanocyte) clusters will not show a coordinated HLA-II program.

**Key Finding:**  
Both B cells and malignant melanocytes expressed multiple core HLA-II genes (DRA/DRB1, DPA1/DPB1, DQB1, DMA/DMB), suggesting a **tumor-cell HLA-II program** with potential implications for **anti–PD-1 therapy response**.

---

## 📊 Data & Methods

- **Dataset:** 10X Genomics *10k Human DTC Melanoma, Chromium GEM-X Single Cell 3'*  
- **Cells:** 10,645 dissociated tumor cells (1 donor, fresh frozen)  
- **Pipeline:**
  - Data import via `Read10X_h5`
  - QC filtering (`nFeature_RNA`, `percent.mt`)
  - Normalization (`LogNormalize`)
  - Variable feature selection
  - Scaling and PCA
  - Clustering (Louvain algorithm)
  - UMAP and tSNE visualization
  - Differential expression with `FindAllMarkers`
  - Cluster annotation via **SingleR** and manual curation
  - HLA-II gene visualization (`VlnPlot`, `FeaturePlot`)

---

## 🧬 Key Results

- **6 identified cell types:** CD4+ Naive T, Activated Effector T, Naive B, Memory B, Memory T, and Melanocytes
- **Significant HLA-II upregulation** in:
  - B cells (expected)
  - Malignant melanocytes (unexpected, tumor-cell intrinsic program)
- Suggestive link between tumor-cell HLA-II expression and **improved immunotherapy response**

---

## 📂 Repository Contents

- `Melanoma_RMarkdown.pdf` – Rendered RMarkdown report with code, plots, and commentary
- `scRNA-seq_Melanoma_Report.pdf` – Condensed research report presentation with background, methods, and interpretation

---

## 🔧 Requirements

- **R (≥ 4.0.0)**
- **R packages:** `Seurat`, `SingleR`, `celldex`, `dplyr`, `patchwork`, `hdf5r`
- **Data:** 10X Genomics HDF5 file (`filtered_feature_bc_matrix.h5`)

---

