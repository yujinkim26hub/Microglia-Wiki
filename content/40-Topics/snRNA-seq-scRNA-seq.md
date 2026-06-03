---
title: snRNA-seq / scRNA-seq
aliases: [snRNA-seq scRNA-seq, snRNA-seq, scRNA-seq, single-cell RNA-seq, single-nucleus RNA-seq, single-cell RNA sequencing]
tags: [topic, methods, scrna-seq, snrna-seq]
created: 2026-06-03
updated: 2026-06-03
type: topic
---

# snRNA-seq / scRNA-seq

> [!abstract] In one line
> Single-cell and single-nucleus RNA sequencing — the workhorse methods for resolving [[microglia|microglial]] [[cell state|states]].

## Overview
scRNA-seq profiles transcriptomes of dissociated single cells; snRNA-seq profiles nuclei, better suited to frozen/archival human brain and reducing dissociation-induced activation artifacts in [[microglia]]. Both enable unbiased discovery of [[cell state|cell states]] and composition shifts.

## Key ideas
- snRNA-seq is often preferred for human post-mortem brain; scRNA-seq can capture more cytoplasmic transcripts.
- Dissociation can artificially induce [[microglia activation]] signatures — a key caveat.
- Enables [[disease-associated microglia]] discovery, [[cell-cell interaction]] inference, and [[gene interaction|GRN]] reconstruction.

## Strengths & limitations
- **Strengths:** unbiased, high-resolution state discovery; scalable.
- **Limitations:** loses spatial context (see [[spatial transcriptomics]]); dropout; dissociation artifacts; ambient RNA.

## Related
- Concepts: [[microglia]], [[cell state]], [[disease-associated microglia]], [[cell-cell interaction]]
- Topics: [[spatial transcriptomics]], [[multi-omics]], [[brain single-cell atlas]]

## Papers
- [[chhatbar-2026-microglia-taxonomy]] — scRNA-seq of >1M CNS cells across >30 conditions.
- [[prater-2023-human-microglia-ad]] — snRNA-seq of human AD microglia.
- [[fujita-2024-cell-subtype-genetic-variation-ad]] — ~1.5M-nucleus snRNA-seq eQTL atlas.
- [[sziraki-2023-easysci-aging-ad]] — EasySci combinatorial-indexing single-cell.
- [[clarence-2025-postnatal-brain-multiome]] — single-nucleus multiome (RNA + ATAC).
- [[jang-2026-singlebrain-sn-eqtl]] — snRNA-seq eQTL meta-analysis (5.8M nuclei).
- [[young-2021-microglia-transcriptional-map]] — single-cell + bulk human microglia.

## Open questions
- How to harmonize states across platforms and labs?
