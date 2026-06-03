---
title: "Kosoy 2025 — AD transcriptional landscape in ex vivo human microglia"
aliases: [Kosoy 2025, "Alzheimer's disease transcriptional landscape in ex vivo human microglia"]
tags: [primary-research, microglia, alzheimers-disease, transcriptomics, neuroinflammation, gene-expression-signature, biomarkers, therapeutic-targets]
authors: "Kosoy R, Fullard JF, Bendl J, Kleopoulos SP, Shao Z, Argyriou S, Mathur D, Psychogyiou K, Malakates P, Vicari J, Ma Y, Humphrey J, Brophy E, Raj T, Katsel P, Voloudakis G, Lee D, Bennett DA, Haroutunian V, Hoffman GE, Roussos P"
year: 2025
journal: "Nature Neuroscience"
doi: "10.1038/s41593-025-02020-2"
pmid: "40760184"
url: "https://www.nature.com/articles/s41593-025-02020-2"
section: "Alzheimer's disease"
created: 2026-06-03
updated: 2026-06-03
type: paper-summary
---

# Alzheimer's disease transcriptional landscape in ex vivo human microglia (Kosoy et al., 2025)

> [!warning] Limited-source summary
> The **final published full text** (*Nature Neuroscience*) was paywalled and not directly accessed. This summary is built from the **published abstract + PubMed (PMID 40760184)** and the **open-access preprint of the same study** (Research Square, doi:10.21203/rs.3.rs-3851590/v1; PMC10854306, CC-BY-4.0). Figure numbering and minor details reflect the preprint and may differ in the published version. No methods, figures, or results have been invented.
>
> Source stub: [[kosoy-2025-source|bibliographic source]].

## Citation
Kosoy R, Fullard JF, Bendl J, Kleopoulos SP, Shao Z, Argyriou S, Mathur D, Psychogyiou K, Malakates P, Vicari J, Ma Y, Humphrey J, Brophy E, Raj T, Katsel P, Voloudakis G, Lee D, Bennett DA, Haroutunian V, Hoffman GE, Roussos P. **Alzheimer's disease transcriptional landscape in ex vivo human microglia.** *Nature Neuroscience.* 2025 Sep;28(9):1830–1843. Epub 2025 Aug 4. doi:[10.1038/s41593-025-02020-2](https://doi.org/10.1038/s41593-025-02020-2). PMID: [40760184](https://pubmed.ncbi.nlm.nih.gov/40760184/).
Preprint (open access): Research Square, 2024. doi:10.21203/rs.3.rs-3851590/v1; [PMC10854306](https://pmc.ncbi.nlm.nih.gov/articles/PMC10854306/).

## Core question
How is the transcriptome of human brain [[microglia]] altered across the clinical and neuropathological severity of [[Alzheimer's disease]], and which genes, isoforms, and gene networks are dysregulated?

## Prior studies
Microglia are genetically and biologically implicated in [[Alzheimer's disease]] (myeloid-enriched GWAS risk genes; the [[disease-associated microglia|DAM]] concept). Most prior molecular characterization came from mouse models or from bulk brain homogenate / single-cell snapshots, which dilute the microglial signal (microglia are <10% of brain cells).

## Limitations of prior studies
- Bulk-tissue studies obscure microglia-specific signals (3.4× smaller effect sizes than purified microglia; some genes change in opposite directions).
- 3′ single-cell methods cannot resolve transcript/isoform-level switching.
- Few datasets span the **full** clinical + pathological AD spectrum in **purified human** microglia at sufficient sample size.

## What this study did
The authors FACS-purified microglia from fresh prefrontal cortex of 189 postmortem human brains spanning healthy aging to severe AD, performed bulk total-RNA-seq, and analyzed the data at gene, transcript/isoform, gene–gene-coordination, co-expression-module, and patient-trajectory levels.

## Main results of this study
- **Cohort:** 189 brains (~182 after QC), 58 healthy aging controls and 131 with disease phenotypes, including 63 across the full AD spectrum (Mount Sinai Brain Bank + Rush ADRC).
- **Differential expression vs. AD phenotypes:** *PTPRG* (strongest up), *IL15*, *APOE* up; *CECR2*, *SELENBP1*, *ASTN1*, *MEIS1*, *TNFRSF21* down; dementia-specific signals (*SLC46A1*, *LFNG*).
- **Pathways:** downregulation of inflammatory/immune programs (interferon-α/γ, TNFα/NF-κB) with AD, alongside upregulation of oxidative phosphorylation and ribosomal/stress programs — immune pathways rise with age but fall with AD.
- **Transcript level:** omnibus (RE2C) testing found 260 genes with heterogeneous isoform effects (88 missed by gene-level tests), e.g. *SERPINF1* (an isoform targeted by nonsense-mediated decay) and *PDPN* (isoform effect in *APOE4* carriers).
- **Gene–gene coordination:** ~17.3% of the transcriptome shows altered correlation with *PTPRG* in AD ([[gene interaction|loss of coordination]] with partners such as *LRP1*, *VEGFB*, *SLC44A2*).
- **Co-expression modules (MEGENA):** 306 sizeable modules; module **M925** (drivers *CECR2*, *MORN1*, *SELENBP1*, *IL15*) enriched across AD phenotypes; **M114** APOE-anchored / lipid metabolism; immune modules (M123/M444) enriched for MS / rheumatoid-arthritis genes.
- **Patient subtypes:** pseudotime/trajectory analysis defined 6 clusters — two control, two AD (distinct trajectories, e.g. younger/possibly aggressive vs. older/slower) — with distinct molecular states (immune, stress, MYC targets, interferon).
- **Genetics vs. expression:** AD DEG signatures were **not** enriched for AD GWAS risk at genome-wide level (downregulated genes were enriched for MS/RA GWAS), suggesting risk acts upstream while expression captures secondary/disease-state changes.

## Limitations of this study
- Single brain region (prefrontal cortex / BA10); postmortem tissue and ex vivo (not in vivo) measurement; PMI as covariate.
- Fresh-tissue requirement limits availability.
- Strong age–AD correlation complicates age-independent interpretation.
- Bulk (not single-cell) microglia: cannot assign signals to specific microglial [[cell state|states]] directly.
- Transcript-level power limited by low per-transcript counts / multiple testing.

## Methods
FACS isolation of CD45⁺CD11b⁺ microglia from fresh prefrontal cortex; RNA via PicoPure; libraries via SMARTer Stranded Total RNA-seq; sequencing on NovaSeq 6000 / HiSeq2500; alignment to GRCh38; transcript quantification with kallisto. Analyses: `dream` mixed-model [[differential gene expression|DEG]] across AD phenotypes (CERAD, Braak, amyloid-β, CDR, *APOE4* dose); RE2C transcript omnibus; gene–gene correlation analysis; MEGENA co-expression networks; pseudotime/trajectory clustering; `zenith`/HALLMARK enrichment; MAGMA GWAS enrichment. (Bulk RNA-seq, related to [[transcriptomics]]; not single-cell.)

## Key figures
*(Figure numbering from the open-access preprint version.)*
- **Fig 1** — Cohort and AD measures (age, Braak, amyloid-β, CDR) and their correlations.
- **Fig 2** — DEGs across AD phenotypes; volcano plots; pathway enrichment; comparison to published signatures.
- **Fig 3** — Transcript-level omnibus results; *PTPRG* (concordant) vs. *SERPINF1* (heterogeneous) isoform effects.
- **Fig 4** — AD-dysregulated gene–gene interactions; *PTPRG* interactome.
- **Fig 5** — MEGENA co-expression modules annotated by DEG/GWAS; M925 network.
- **Fig 6** — Pseudotime trajectory with 6 patient clusters and their molecular states.

## Main findings
- Purified human microglia reveal AD-associated changes far stronger and sometimes opposite to bulk tissue.
- AD is accompanied by **down**regulation of microglial immune/interferon programs (distinct from a simple "activation" narrative).
- Isoform-level and gene–gene-coordination changes add disease signal beyond standard DEG analysis.
- Patient-level molecular heterogeneity defines candidate AD subtypes.

## Relevance to microglia and neurological disease
A large, purified-microglia human resource defining the AD-associated microglial [[transcriptomics|transcriptome]] and nominating candidate genes/modules for [[biomarkers]] and [[therapeutic targets]]; directly informs [[microglia]], [[neuroinflammation]], and [[disease-associated microglia]] in the context of [[Alzheimer's disease]].

## Connection to other papers
- Complements [[chhatbar-2026-microglia-taxonomy]] — that study's single-cell [[brain single-cell atlas|taxonomy]] of microglial [[cell state|states]] provides a state framework into which this bulk human-AD signature can be resolved/placed.
- Contextualized by [[shimizu-2025-microglia-evolution]] — human vs. rodent microglial divergence and the biphasic AD role of microglia discussed there frame why human purified-microglia data are needed.

## Related concepts
[[microglia]] · [[Alzheimer's disease]] · [[neuroinflammation]] · [[disease-associated microglia]] · [[transcriptomics]] · [[differential gene expression]] · [[gene expression signature]] · [[gene interaction]] · [[gene relationship]] · [[biomarkers]] · [[therapeutic targets]] · [[APOE]] · [[brain region]]

## Open questions
- Which bulk AD signatures map to which single-cell microglial [[cell state|states]] (resolvable via [[chhatbar-2026-microglia-taxonomy|the taxonomy]])?
- Is the apparent immune/interferon downregulation a late-stage exhaustion phenomenon?
- Do other [[brain region|regions]] show the same microglial AD landscape?
- _Final published full text not accessed — confirm published figure numbering and any added analyses._

## Tags
#primary-research #microglia #alzheimers-disease #transcriptomics #neuroinflammation #gene-expression-signature #biomarkers #therapeutic-targets
