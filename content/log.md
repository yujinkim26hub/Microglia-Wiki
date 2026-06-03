---
title: Log
aliases: [log, Log, changelog]
tags: [meta]
created: 2026-06-03
updated: 2026-06-03
type: log
---

# 🪵 Log

Append-only changelog of wiki edits made by the agent. Newest entries at the top.
Format: `YYYY-MM-DD — what changed (links)`.

---

- **2026-06-03** — **Fixed summary/source slug collision.** Source stubs and summaries had shared basenames (e.g. `kosoy-2025-ad-microglia-landscape.md` in both `00-Sources/` and `10-Summaries/`), so Quartz's shortest-basename resolution sent every `[[…]]` paper link to the **source stub**, leaving the summaries unreachable ("missing" on the site). Renamed sources to `*-source.md` (`kosoy-2025-source`, `chhatbar-2026-source`, `shimizu-2025-source`); rewrote the three [[10-Summaries/kosoy-2025-ad-microglia-landscape|summaries]] with the exact unnumbered 15-section schema; pointed each source's "Structured summary" link at the summary; updated [[index|home]]/[[catalog]] and `10-Summaries/index.md` to link summaries; added a naming rule to `AGENTS.md §3/§5` to prevent recurrence. All wikilinks re-audited (now also checking for ambiguous basenames).

- **2026-06-03** — Ingested **Shimizu & Prinz (2025)**, "Microglia across evolution" (*Cellular & Molecular Immunology*; review, open access). Verified (PMID 41272275 / PMC12660708). Created [[shimizu-2025-microglia-evolution]] + source stub; linked to [[microglia]], [[development stage]], [[cell state]], [[CSF1R]], [[TREM2]], [[Alzheimer's disease]]; cross-linked to [[chhatbar-2026-microglia-taxonomy]] (shared authors) and [[kosoy-2025-ad-microglia-landscape]].
- **2026-06-03** — Ingested **Chhatbar et al. (2026)**, "A transcriptomic microglia taxonomy across mouse and human pathologies" (*Nature Immunology*). Verified (PMID 41882205). **Limited-source** (full text paywalled; abstract/PubMed only). Created [[chhatbar-2026-microglia-taxonomy]] + source stub; created new [[CSF1R]] gene entity; updated [[disease-associated microglia]], [[microglia activation]], [[cell state]], [[brain single-cell atlas]], [[spatial transcriptomics]], [[snRNA-seq scRNA-seq]]; cross-linked to the other two papers.
- **2026-06-03** — Ingested **Kosoy et al. (2025)**, "Alzheimer's disease transcriptional landscape in ex vivo human microglia" (*Nature Neuroscience*). Verified (PMID 40760184). **Limited-source** for final version (published full text paywalled; details from published abstract + open-access preprint PMC10854306). Created [[kosoy-2025-ad-microglia-landscape]] + source stub; updated [[Alzheimer's disease]], [[APOE]], [[microglia]], [[neuroinflammation]], [[transcriptomics]], [[differential gene expression]], [[gene expression signature]]; cross-linked to the other two papers.
- **2026-06-03** — Updated [[catalog]] with the three papers (table + by-topic + by-disease).
- **2026-06-03** — Started a transcriptomics scope expansion: added seed concept pages [[transcriptomics]], [[single-cell transcriptomics]], [[differential gene expression]], [[gene expression signature]] (marked as seed notes needing paper-backed refinement). _Scope-doc edits and remaining transcriptomics pages still pending._
- **2026-06-03** — Initialized the wiki: created folder structure, [[index]], [[catalog]], seed concept/entity/topic pages, templates, and the paper-ingestion workflow. No papers ingested yet.
