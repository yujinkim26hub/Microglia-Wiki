---
title: Differential gene expression
aliases: [differential gene expression, Differential gene expression, differential expression, DGE, DEG]
tags: [concept, transcriptomics, seed, needs-refinement]
created: 2026-06-03
updated: 2026-06-03
type: concept
---

# Differential gene expression

> [!warning] Seed note
> This is a **seed page** that needs paper-backed refinement. It will be expanded and cited as papers are ingested.

> [!abstract] In one line
> The identification of genes whose expression differs between conditions, cell types, or [[cell state|states]] — the core comparison of [[transcriptomics]].

## Definition
Differential gene expression (DGE) analysis statistically compares transcript abundance between groups (e.g., disease vs. control, [[disease-associated microglia]] vs. homeostatic [[microglia]]) to identify differentially expressed genes (DEGs). It is a foundational step in both bulk and [[single-cell transcriptomics]].

## Why it matters for microglia / neurological disease
DGE defines the molecular differences between microglial [[cell state|states]] and disease contexts, producing the gene lists that become [[gene expression signature|expression signatures]], candidate [[biomarkers]], and [[therapeutic targets]] across [[neurodegenerative disease|neurodegenerative]] and other conditions.

## Key points
- Common tools: DESeq2, edgeR, limma (bulk); Wilcoxon/MAST and pseudobulk approaches (single-cell).
- Outputs drive [[gene expression signature|signatures]] and enrichment / pathway analysis.
- In single-cell data, pseudobulk-per-sample methods reduce false positives.

## Related
- Concepts: [[transcriptomics]], [[single-cell transcriptomics]], [[gene expression signature]], [[cell state]], [[gene relationship]], [[biomarkers]], [[microglia]]
- Topics: [[snRNA-seq scRNA-seq]], [[multi-omics]]

## Papers
- [[kosoy-2025-ad-microglia-landscape]] — DEG across AD phenotypes at gene and transcript/isoform level.

## Open questions
- _To be refined as papers are ingested._
