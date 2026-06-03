---
title: Microglia Wiki
aliases: [home, Home, Microglia Wiki]
tags: [meta]
created: 2026-06-03
updated: 2026-06-03
type: index
---

# 🧠 Microglia Wiki

A plain-Markdown, **LLM-maintained research wiki** on **microglia and neurological disease** — an [Obsidian](https://obsidian.md) vault published as a [Quartz](https://quartz.jzhao.xyz/) site, in the spirit of Karpathy's [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f#llm-wiki).

> [!info] Start here
> - **[[catalog/index|Catalog]]** — every paper summary, indexed.
> - **[[log/index|Log]]** — changelog of what the wiki agent has done.
> - Add a paper → see [[unresolved-paper-requests|how ingestion works]] and `AGENTS.md`.

## What lives here

| Layer | Folder | What it is |
|---|---|---|
| 📄 Sources | `00-Sources/` | Bibliographic stubs (DOI / PMID / link) |
| 📝 Summaries | `10-Summaries/` | Structured 15-section paper summaries |
| 🧬 Entities | `20-Entities/` | Genes, diseases, brain regions |
| 💡 Concepts | `30-Concepts/` | Reusable ideas (microglia, neuroinflammation, …) |
| 🔬 Topics | `40-Topics/` | Methods & cross-cutting areas (scRNA-seq, spatial, …) |
| 🗒️ Notes | `50-Notes/` | Free-form notes + unresolved requests |
| ⚙️ Meta | `90-Meta/` | Templates |

## Core concepts

[[microglia]] · [[neuroinflammation]] · [[disease-associated microglia]] · [[microglia activation]] · [[cell state]] · [[cell-cell interaction]] · [[gene relationship]] · [[gene interaction]] · [[biomarkers]] · [[therapeutic targets]]

## Disease focus

[[Alzheimer's disease]] · [[neurodegenerative disease]] · [[neurodevelopmental disease]] · [[neuropsychiatric disease]]

## Methods & data

[[snRNA-seq scRNA-seq]] · [[spatial transcriptomics]] · [[multi-omics]] · [[brain single-cell atlas]] · [[brain region]] · [[development stage]]

---

## Add a paper

Give the agent:

```
First author:
Title:
Year:
Journal:
Section:
```

The agent verifies the paper, writes a 15-section summary, and wires it into the [[catalog/index|Catalog]], [[log/index|Log]], and related concept/topic/entity pages. Unverifiable requests go to [[unresolved-paper-requests]] — never guessed.
