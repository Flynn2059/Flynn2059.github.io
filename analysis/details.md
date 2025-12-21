---
layout: page
title: Analysis Details
permalink: /analysis/details/
---

# Analysis Details

This page provides additional details on my analytical philosophy,
methodological choices, and practical considerations in single-cell
multi-omic data analysis.
<br>
The focus is not on exhaustive pipelines, but on **why specific methods
are chosen and how common analytical pitfalls are avoided**, especially
in the context of peer review.

---

## General Principles

- Analytical choices are driven by biological questions, not by default pipelines  
- Statistical assumptions are made explicit whenever possible  
- Conservative decisions are preferred over aggressive overfitting  
- Visual clarity never overrides biological plausibility  

---

## Quality Control (QC)

Quality control is performed in a **sample-specific manner**, rather than
using fixed global thresholds.
<br>

Metrics considered include:
<br>
- Number of detected genes
- Total UMI counts
- Mitochondrial gene fraction
- Hemoglobin gene expression

Thresholds are determined by inspecting distribution patterns within
each sample, aiming to balance signal preservation and noise removal.

---

## Batch Effect Correction

Batch correction strategies are selected based on:
- Experimental design
- Strength of batch effects
- Risk of biological overcorrection

Methods commonly evaluated include:
Harmony, CCA/rPCA, BBKNN, and scVI.
<br>
The primary goal is to reduce technical variation while preserving
true biological heterogeneity.

---

## Cell Type Annotation

Cell annotation follows a **hierarchical and iterative strategy**:
<br>
1. Initial low-resolution clustering  
2. Identification of major cell lineages  
3. Progressive refinement into functional subpopulations  

This approach avoids forced overannotation and aligns with reviewer
expectations regarding interpretability and reproducibility.

---

## Differential Expression Analysis

Whenever applicable, differential expression is performed using a
**Pseudobulk framework** combined with DESeq2.
<br>
Cells are aggregated at the sample or condition level to avoid
pseudo-replication error caused by treating individual cells as independent
biological replicates.

---

## Immune Repertoire (VDJ) Analysis

Immune repertoire data are re-quantified using MiXCR.
<br>

Two parallel representations are generated:
- Allele-aware data for clonotype similarity and public clonotype analysis
- Allele-collapsed data for clonal expansion and diversity analysis

This design allows flexibility across different analytical objectives.

---

## Scope and Limitations

Not all datasets support all types of analyses.
<br>

Method selection depends on:
<br>
- Sample size and replication
- Biological context
- Data quality and experimental design

Analyses are adapted accordingly to ensure statistical validity and
interpretability.

---

## Contact

If you would like to discuss whether a specific dataset or study design
is suitable for a particular analysis strategy, feel free to **[email me](mailto:jiangxlong@mail2.sysu.edu.cn)**.

