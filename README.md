# Microglia Wiki

An **LLM-maintained research wiki** focused on **microglia and neurological disease**.

This repository is three things at once:

1. **An Obsidian vault** — open the `content/` folder as a vault and use wikilinks, graph view, and templates.
2. **A Markdown-based LLM-maintained research wiki** — papers, concepts, entities, and topics are written as plain Markdown and curated by an LLM agent (see [`CLAUDE.md`](CLAUDE.md) / [`AGENTS.md`](AGENTS.md)).
3. **A Quartz website** — published to GitHub Pages from the same Markdown (see [Publishing](#publishing)).

The design follows Andrej Karpathy's [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f#llm-wiki) idea: a personal, plain-text knowledge base that an LLM keeps tidy, interlinked, and growing — **no vector database, no app server, just Markdown**.

---

## Scope

Microglia biology and its role across neurological, neurodegenerative, neurodevelopmental, and neuropsychiatric disease, viewed primarily through modern single-cell / spatial / multi-omics methods.

Core themes: [[microglia]] · [[neuroinflammation]] · [[disease-associated microglia]] · [[microglia activation]] · [[neurodegenerative disease]] · [[neurodevelopmental disease]] · [[neuropsychiatric disease]] · [[Alzheimer's disease]] · [[cell state]] · [[cell-cell interaction]] · [[gene relationship]] · [[gene interaction]] · [[brain region]] · [[development stage]] · [[brain single-cell atlas]] · [[snRNA-seq scRNA-seq]] · [[spatial transcriptomics]] · [[multi-omics]] · [[biomarkers]] · [[therapeutic targets]]

---

## Repository layout

```
content/
├── index.md          # wiki home / entry point
├── catalog.md        # master index of every paper summary
├── log.md            # append-only changelog of wiki edits
├── 00-Sources/       # raw source metadata (DOIs, links, bibliographic stubs)
├── 10-Summaries/     # one structured summary per paper (15-section schema)
├── 20-Entities/      # concrete named things: genes, diseases, brain regions
│   ├── genes/
│   ├── diseases/
│   └── brain-regions/
├── 30-Concepts/      # reusable ideas: microglia, neuroinflammation, cell state, ...
├── 40-Topics/        # methods & cross-cutting areas: scRNA-seq, spatial, atlases
├── 50-Notes/         # free-form notes + unresolved-paper-requests.md
└── 90-Meta/
    └── templates/    # Obsidian templates (paper summary, concept, entity, topic)
```

Numeric prefixes keep folders ordered in both Obsidian's file explorer and Quartz's sidebar.

---

## How to add a paper

Give the agent these five fields:

```
First author:
Title:
Year:
Journal:
Section:
```

The agent will: search for and **verify** the paper, create a structured summary in `10-Summaries/`, and update `catalog.md`, `log.md`, related concept/topic pages, and cross-links to other papers.

If the paper **cannot be confidently identified, it is not guessed** — it is recorded in [`content/50-Notes/unresolved-paper-requests.md`](content/50-Notes/unresolved-paper-requests.md) as *needs verification*.

Full rules: [`AGENTS.md`](AGENTS.md) and [`CLAUDE.md`](CLAUDE.md).

---

## Using it as an Obsidian vault

1. Install [Obsidian](https://obsidian.md).
2. *Open folder as vault* → select the **`content/`** folder.
3. (Optional) Enable the core **Templates** plugin and point it at `90-Meta/templates/`.

Wikilinks (`[[microglia]]`), tags (`#microglia`), and the graph view work out of the box.

---

## Publishing

The site is built with [Quartz v4](https://quartz.jzhao.xyz/) and deployed to **GitHub Pages** by the workflow in [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml).

The workflow clones Quartz at build time, copies this repo's `content/` into it, applies [`quartz.config.ts`](quartz.config.ts), builds the static site, and publishes it. To enable:

1. Repo **Settings → Pages → Build and deployment → Source: GitHub Actions**.
2. Push to `main`. The site builds and deploys automatically.

See [`docs/PUBLISHING.md`](docs/PUBLISHING.md) for details, including running Quartz locally.

---

## Principles

- **Plain Markdown only.** No database, no proprietary format. Everything is greppable and diffable.
- **Linked, not siloed.** Every page connects to concepts, entities, topics, and other papers.
- **Verifiable.** Every claim traces to a cited source; unverifiable paper requests are quarantined, not invented.
- **Simple and usable today.** No vector DB, no build step required just to read or edit.
