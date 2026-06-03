# AGENTS.md — Operating manual for the LLM curator

This file defines how an LLM agent maintains the **Microglia Wiki**. It is the single source of truth for conventions; `CLAUDE.md` defers to it.

The wiki follows Karpathy's [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f#llm-wiki): a plain-Markdown, interlinked knowledge base that an LLM keeps tidy and growing. **No vector database. No guessing. Everything traces to a source.**

---

## 1. Golden rules

1. **Plain Markdown only.** No databases, no generated binary artifacts in `content/`.
2. **Never invent a citation, DOI, result, or figure.** If you cannot verify it, say so and quarantine it (§5).
3. **Everything is linked.** Every page should connect outward via `[[wikilinks]]`. A page with no links is incomplete.
4. **Append, don't rewrite history.** `log.md` is append-only. Edit pages freely, but record what you did.
5. **One paper = one summary file** in `10-Summaries/`, following the 15-section schema (§4) exactly.
6. **Prefer existing pages.** Before creating a concept/entity/topic page, check whether one already exists (search the relevant folder). Reuse and link; don't duplicate.

---

## 2. Folder model

| Folder | Holds | Example |
|---|---|---|
| `00-Sources/` | Bibliographic stubs: DOI, link, authors, abstract pointer. One per paper. | `keren-shaul-2017-art.md` |
| `10-Summaries/` | Structured 15-section summary. One per paper. | `keren-shaul-2017-dam.md` |
| `20-Entities/` | Concrete named things. Subfolders: `genes/`, `diseases/`, `brain-regions/`. | `genes/TREM2.md`, `diseases/Alzheimers-disease.md` |
| `30-Concepts/` | Reusable abstract ideas. | `microglia.md`, `neuroinflammation.md`, `cell-state.md` |
| `40-Topics/` | Methods & cross-cutting areas. | `snRNA-seq-scRNA-seq.md`, `spatial-transcriptomics.md` |
| `50-Notes/` | Free-form notes; **`unresolved-paper-requests.md`** lives here. | `unresolved-paper-requests.md` |
| `90-Meta/templates/` | Templates. Copy these to start new pages. | `paper-summary.md` |

`Section` (from the ingestion request) maps to a `40-Topics/` page (or a `30-Concepts/` page if it is conceptual). Use it to file and cross-link the summary.

---

## 3. Naming & linking conventions

- **Filenames:** lowercase, hyphenated, ASCII. Strip apostrophes. e.g. `Alzheimer's disease` → `Alzheimers-disease.md`.
- **Paper summary filenames:** `firstauthor-year-shortslug.md` (e.g. `keren-shaul-2017-dam.md`). Lowercase the author surname.
- **Source-stub filenames:** `firstauthor-year-source.md` (e.g. `keren-shaul-2017-source.md`). **The source stub and its summary MUST have different basenames** — never give them the same filename in different folders. Quartz resolves wikilinks by *shortest basename*, so two files sharing a basename make every `[[basename]]` link ambiguous (it silently points to only one of them, orphaning the other). The bare `[[firstauthor-year-shortslug]]` link must uniquely identify the **summary**.
- **Wikilinks** use the human-readable display form: `[[microglia]]`, `[[Alzheimer's disease]]`, `[[neuroinflammation]]`, `[[disease-associated microglia]]`. If display text differs from the filename, use an alias in the target page's frontmatter `aliases:` list so Obsidian and Quartz resolve it. Always add a matching alias when you introduce a new display form.
- **Tags:** lowercase, hyphenated, in YAML frontmatter `tags:`. Reuse the controlled vocabulary in §6 before inventing new tags.
- **Every page** starts with YAML frontmatter: `title`, `aliases`, `tags`, `created`, `updated`, `type`.

---

## 4. Paper summary schema (REQUIRED — all 15 sections, in order)

Every file in `10-Summaries/` MUST contain these sections. Use the template at `90-Meta/templates/paper-summary.md`. If a section is genuinely unknown after honest effort, write `*Not determined from available sources.*` — do not fabricate.

1. **Citation** — full bibliographic citation + DOI/PMID + link.
2. **Core question** — the central question the paper asks.
3. **Prior studies** — what was known / the prior work it builds on.
4. **Limitations of prior studies** — the gap that motivated this work.
5. **What this study did** — the approach in 1–3 sentences.
6. **Main results of this study** — concrete findings (this is the detailed results section).
7. **Limitations of this study** — caveats acknowledged or evident.
8. **Methods** — datasets, model systems, assays, key analyses.
9. **Key figures** — the figures that carry the argument, with one line each.
10. **Main findings** — the durable take-home points (bulleted, distilled from §6).
11. **Relevance to microglia and neurological disease** — why it matters to this wiki's scope.
12. **Connection to other papers** — `[[wikilinks]]` to other summaries (agrees with / extends / contradicts).
13. **Related concepts** — `[[wikilinks]]` to `30-Concepts/`, `20-Entities/`, `40-Topics/`.
14. **Open questions** — what remains unanswered.
15. **Tags** — controlled-vocabulary tags (also mirror these into frontmatter).

---

## 5. Paper ingestion workflow

Trigger: the user supplies
```
First author:
Title:
Year:
Journal:
Section:
```

Steps:

1. **Search** for the paper (web search; try title + first author + year, then DOI/PMID lookup).
2. **Verify identity.** A paper is *confidently identified* only when the retrieved record matches the user's fields — first author surname, title (allowing minor wording differences), year (±1 for online-vs-print), and journal are consistent, and you have a real DOI or PMID. When in doubt, treat as **not** identified.
3. **If identified:**
   a. Create `00-Sources/firstauthor-year-source.md` (bibliographic stub with DOI/PMID/link). **Keep stubs stub-only — never put the 15-section summary in `00-Sources/`.**
   b. Create `10-Summaries/firstauthor-year-shortslug.md` from the template — fill **all 15 sections** from the actual paper (abstract + available full text/figures). Never fabricate results; cite what you read. The summary's basename must differ from the source's (see §3) so `[[firstauthor-year-shortslug]]` uniquely points to the summary.
   c. Update **`catalog.md`** — add a row (author, year, title, journal, summary link, tags).
   d. Append to **`log.md`** — dated one-line entry of what was added/changed.
   e. Update related **concept** pages (`30-Concepts/`), **topic/Section** page (`40-Topics/`), and **entity** pages (`20-Entities/`) — add the new summary under their "Papers" / "Related papers" list and create missing concept/entity/topic pages as needed (from templates, fully linked).
   f. **Connect to other papers** — in §12 of the new summary and reciprocally in related summaries, add `[[wikilinks]]` describing the relationship.
4. **If NOT confidently identified:** do **not** create a summary and do **not** guess. Append an entry to **`content/50-Notes/unresolved-paper-requests.md`** under "Needs verification," recording all five supplied fields, what you searched, why it failed (ambiguous / no match / multiple candidates), and any candidate DOIs found. Tell the user it needs verification.

Always state plainly which path you took.

---

## 6. Controlled vocabulary (seed tags)

Reuse these before inventing new ones (add hyphens; lowercase):

`microglia` · `neuroinflammation` · `disease-associated-microglia` · `dam` · `microglia-activation` · `neurodegenerative-disease` · `neurodevelopmental-disease` · `neuropsychiatric-disease` · `alzheimers-disease` · `cell-state` · `cell-cell-interaction` · `gene-relationship` · `gene-interaction` · `brain-region` · `development-stage` · `brain-single-cell-atlas` · `scrna-seq` · `snrna-seq` · `spatial-transcriptomics` · `multi-omics` · `biomarkers` · `therapeutic-targets` · `methods` · `review` · `primary-research`

---

## 7. Maintenance tasks (beyond ingestion)

- **Catalog hygiene:** keep `catalog.md` sorted and every summary listed.
- **Link repair:** when renaming a page, update inbound `[[wikilinks]]` and `aliases`.
- **Concept growth:** as summaries accumulate, enrich concept pages with synthesized cross-paper insight (always cited back to summaries).
- **Log everything notable** in `log.md`.

---

## 8. What NOT to do

- Do not add a vector database, embeddings store, or app backend. (Explicitly out of scope for now.)
- Do not fabricate citations, numbers, figure descriptions, or conclusions.
- Do not create orphan pages with no links.
- Do not silently drop the user's request — if unverifiable, quarantine it visibly.
