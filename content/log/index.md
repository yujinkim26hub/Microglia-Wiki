---
title: Log
aliases: [log, Log]
tags: [meta, log]
created: 2026-06-03
updated: 2026-06-03
type: log
---

# 🪵 Log

Append-only changelog of wiki edits made by the agent. Newest entries at the top.
Format: `YYYY-MM-DD — what changed (links)`.

---

- **2026-06-03** — **Batch-ingested 11 papers** (Nature Genetics/Aging genetics-of-microglia & brain-genomics series). Verified each (author/title/year/journal + DOI/PMID/PMCID); all paywalled → **limited-source** summaries (abstract/PubMed-grounded, no invented figures/results). Created summaries + distinct `*-source.md` stubs for: [[de-paiva-lopes-2022-microglia-transcriptome-atlas|de Paiva Lopes 2022]], [[prater-2023-human-microglia-ad|Prater 2023]], [[kosoy-2022-microglia-regulome|Kosoy 2022 (regulome)]], [[young-2021-microglia-transcriptional-map|Young 2021]], [[yang-2023-ad-variants-microglia|Yang 2023]], [[jang-2026-singlebrain-sn-eqtl|Jang 2026 (SingleBrain)]], [[fujita-2024-cell-subtype-genetic-variation-ad|Fujita 2024]], [[sziraki-2023-easysci-aging-ad|Sziraki 2023 (EasySci)]], [[clarence-2025-postnatal-brain-multiome|Clarence 2025]], [[schwartzentruber-2021-ad-gwas-finemapping|Schwartzentruber 2021]], [[jagadeesh-2022-sc-linker|Jagadeesh 2022 (sc-linker)]]. Created new gene entities [[SPI1]] and [[BIN1]]. Updated [[catalog/index|Catalog]] (now a bullet list with By-topic/By-disease), and concept/topic/entity Papers sections. Cross-linked the genetics-of-microglia cluster.
  - **Duplicate detected & merged:** input rows #1 and #5 (Katia de Paiva Lopes 2022, *Nature Genetics*) are the **same paper** — ingested once, listed once in the catalog (assigned brain region + development stage + gene relationship).
  - **Already present, skipped:** input row #3 (Kosoy 2025, *Nature Neuroscience*, "AD transcriptional landscape in ex vivo human microglia") was already ingested as [[kosoy-2025-ad-microglia-landscape]] — not re-created.
- **2026-06-03** — **Fixed Catalog/Log 404s.** The root `catalog.md` / `log.md` had self-referential aliases (`catalog` / `log` equal to their own slugs), so Quartz's `AliasRedirects` emitted a redirect at `/catalog` and `/log` that collided with the real content pages → 404. Converted both to **folder-style index pages** (`catalog/index.md`, `log/index.md`) served at `/catalog/` and `/log/`; updated all links to path-qualified [[catalog/index|Catalog]] / [[log/index|Log]]; deleted the old root files. Verified with a local Quartz build.
- **2026-06-03** — Standardized all Catalog/Log references to wikilinks and added `30-Concepts/` and `40-Topics/` folder index pages with a Catalog/Log nav.
- **2026-06-03** — **Fixed summary/source slug collision.** Source stubs and summaries had shared basenames (e.g. `kosoy-2025-ad-microglia-landscape.md` in both `00-Sources/` and `10-Summaries/`), so Quartz's shortest-basename resolution sent every `[[…]]` paper link to the **source stub**, leaving the summaries unreachable ("missing" on the site). Renamed sources to `*-source.md` (`kosoy-2025-source`, `chhatbar-2026-source`, `shimizu-2025-source`); rewrote the three [[10-Summaries/kosoy-2025-ad-microglia-landscape|summaries]] with the exact unnumbered 15-section schema; pointed each source's "Structured summary" link at the summary; updated [[index|home]]/[[catalog/index|Catalog]] and `10-Summaries/index.md` to link summaries; added a naming rule to `AGENTS.md §3/§5` to prevent recurrence. All wikilinks re-audited (now also checking for ambiguous basenames).

- **2026-06-03** — Ingested **Shimizu & Prinz (2025)**, "Microglia across evolution" (*Cellular & Molecular Immunology*; review, open access). Verified (PMID 41272275 / PMC12660708). Created [[shimizu-2025-microglia-evolution]] + source stub; linked to [[microglia]], [[development stage]], [[cell state]], [[CSF1R]], [[TREM2]], [[Alzheimer's disease]]; cross-linked to [[chhatbar-2026-microglia-taxonomy]] (shared authors) and [[kosoy-2025-ad-microglia-landscape]].
- **2026-06-03** — Ingested **Chhatbar et al. (2026)**, "A transcriptomic microglia taxonomy across mouse and human pathologies" (*Nature Immunology*). Verified (PMID 41882205). **Limited-source** (full text paywalled; abstract/PubMed only). Created [[chhatbar-2026-microglia-taxonomy]] + source stub; created new [[CSF1R]] gene entity; updated [[disease-associated microglia]], [[microglia activation]], [[cell state]], [[brain single-cell atlas]], [[spatial transcriptomics]], [[snRNA-seq scRNA-seq]]; cross-linked to the other two papers.
- **2026-06-03** — Ingested **Kosoy et al. (2025)**, "Alzheimer's disease transcriptional landscape in ex vivo human microglia" (*Nature Neuroscience*). Verified (PMID 40760184). **Limited-source** for final version (published full text paywalled; details from published abstract + open-access preprint PMC10854306). Created [[kosoy-2025-ad-microglia-landscape]] + source stub; updated [[Alzheimer's disease]], [[APOE]], [[microglia]], [[neuroinflammation]], [[transcriptomics]], [[differential gene expression]], [[gene expression signature]]; cross-linked to the other two papers.
- **2026-06-03** — Updated [[catalog/index|Catalog]] with the three papers (table + by-topic + by-disease).
- **2026-06-03** — Started a transcriptomics scope expansion: added seed concept pages [[transcriptomics]], [[single-cell transcriptomics]], [[differential gene expression]], [[gene expression signature]] (marked as seed notes needing paper-backed refinement). _Scope-doc edits and remaining transcriptomics pages still pending._
- **2026-06-03** — Initialized the wiki: created folder structure, [[index]], [[catalog/index|Catalog]], seed concept/entity/topic pages, templates, and the paper-ingestion workflow. No papers ingested yet.
