---
title: "Jagadeesh 2022 — sc-linker: disease-critical cell types and processes from scRNA-seq + genetics"
aliases: [Jagadeesh 2022, sc-linker, "Identifying disease-critical cell types and cellular processes by integrating single-cell RNA-sequencing and human genetics"]
tags: [primary-research, gene-relationship, scrna-seq, cell-state, neurodegenerative-disease, neuropsychiatric-disease, microglia]
authors: "Jagadeesh KA, Dey KK, Montoro DT, ... Price AL, Regev A"
year: 2022
journal: "Nature Genetics"
doi: "10.1038/s41588-022-01187-9"
pmid: "34845454"
pmcid: "PMC9910198"
url: "https://www.nature.com/articles/s41588-022-01187-9"
section: "gene relationship"
created: 2026-06-03
updated: 2026-06-03
type: paper-summary
---

# Identifying disease-critical cell types and cellular processes by integrating single-cell RNA-sequencing and human genetics (Jagadeesh et al., 2022)

> [!warning] Limited-source summary
> Full text not accessed. Built from the verified published abstract, PubMed (PMID 34845454), and the open-access PMC record (PMC9910198). No methods, figures, or results were invented; unknown specifics are marked.

## Citation
Jagadeesh KA, Dey KK, Montoro DT, et al. **Identifying disease-critical cell types and cellular processes by integrating single-cell RNA-sequencing and human genetics.** *Nature Genetics.* 2022;54(10):1479–1492. doi:[10.1038/s41588-022-01187-9](https://doi.org/10.1038/s41588-022-01187-9). PMID: [34845454](https://pubmed.ncbi.nlm.nih.gov/34845454/); PMCID: PMC9910198. Source stub: [[jagadeesh-2022-source]].

## Core question
Can integrating [[single-cell transcriptomics|scRNA-seq]], epigenomic maps, and GWAS reveal the [[cell state|cell types]] and processes through which genetic variants influence disease ([[gene relationship]])?

## Prior studies
Heritability-partitioning linked GWAS to tissues/annotations, but resolving specific cell types and disease-relevant programs genome-wide was difficult.

## Limitations of prior studies
Bulk annotations lack single-cell resolution; few frameworks connected cell-type programs to GWAS systematically.

## What this study did
Introduced **sc-linker**, a framework integrating scRNA-seq-derived gene programs, enhancer–gene maps, and GWAS summary statistics to infer disease-critical cell types and processes.

## Main results of this study
- Built **sc-linker** linking single-cell programs → enhancers → GWAS heritability across many diseases.
- Recapitulated known biology and surfaced cell–disease relationships (e.g., GABAergic neurons in major depression; disease-specific complement-cascade process in **multiple sclerosis** — relevant to [[microglia]]/[[neuroinflammation]]).
- Provided a general method to attribute heritability to cell-type-specific and disease-dependent programs.

## Limitations of this study
*Not determined from available sources (full text not accessed).* Depends on reference scRNA-seq/enhancer maps and GWAS power.

## Methods
Construction of cell-type/disease gene programs from scRNA-seq; enhancer–gene linking; stratified LD-score-style heritability integration with GWAS. Detailed parameters: *Not determined from available sources.*

## Key figures
*Not determined from available sources (full text not accessed).*

## Main findings
- A reusable framework mapping GWAS to disease-critical cell types/processes.
- Highlights immune/microglial processes (e.g., complement) in neurological disease.

## Connection to other papers
- Methodologically complements AD gene-prioritization [[schwartzentruber-2021-ad-gwas-finemapping]] and cell-type eQTLs [[fujita-2024-cell-subtype-genetic-variation-ad]], [[jang-2026-singlebrain-sn-eqtl]].
- Cell-type attribution relevant to microglia resources [[de-paiva-lopes-2022-microglia-transcriptome-atlas]], [[kosoy-2022-microglia-regulome]].

## Related concepts
[[gene relationship]] · [[cell state]] · [[single-cell transcriptomics]] · [[microglia]] · [[neuroinflammation]] · [[neurodegenerative disease]] · [[neuropsychiatric disease]]

## Open questions
- How sensitive are inferences to the reference single-cell atlas?
- Which microglial programs are disease-causal across disorders?

## Tags
#primary-research #gene-relationship #scrna-seq #cell-state #neurodegenerative-disease #neuropsychiatric-disease #microglia
