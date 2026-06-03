# CLAUDE.md

Guidance for Claude Code (and other LLM agents) working in this repository.

## What this repo is

The **Microglia Wiki**: a plain-Markdown, Obsidian-compatible, LLM-maintained research wiki on **microglia and neurological disease**, published as a Quartz website on GitHub Pages. It follows Karpathy's [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f#llm-wiki) model. **No vector database.**

## Read this first

**`AGENTS.md` is the operating manual.** Follow it exactly. It defines folder roles, naming/linking conventions, the 15-section paper-summary schema, the paper-ingestion workflow, and the controlled tag vocabulary. This file only adds Claude-specific reminders.

## Quick reference

- All wiki content lives under `content/`. Treat it as an Obsidian vault.
- Use Obsidian `[[wikilinks]]` everywhere; keep pages interlinked.
- One paper → one summary in `content/10-Summaries/` using the 15-section schema (template: `content/90-Meta/templates/paper-summary.md`).
- Master index: `content/catalog/index.md`. Changelog (append-only): `content/log/index.md`.

## Paper ingestion (the main workflow)

When the user provides:

```
First author:
Title:
Year:
Journal:
Section:
```

do the full ingestion workflow in **AGENTS.md §5**:

1. Search for the paper and **verify** its identity against the supplied fields (need a real DOI/PMID and consistent author/title/year/journal).
2. **If verified:** create the source stub + 15-section summary, then update `catalog/index.md`, `log/index.md`, and the related concept/topic/entity pages, and cross-link to other papers.
3. **If NOT confidently verified: do not guess.** Append it to `content/50-Notes/unresolved-paper-requests.md` as *needs verification* and tell the user.

Always say which path you took and what files you changed.

## Hard rules (do not break)

- Never fabricate a citation, DOI, statistic, figure, or conclusion.
- Never add a vector DB, embeddings, or server backend — out of scope for now.
- Never leave a new page orphaned (no wikilinks).
- Keep everything plain Markdown and greppable.

## Publishing

The Quartz site builds via `.github/workflows/deploy.yml` (clones Quartz, copies `content/`, applies `quartz.config.ts`, deploys to Pages). Editing Markdown is enough; the workflow handles the build. See `docs/PUBLISHING.md`.
