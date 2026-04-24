# LLM Wiki

A personal knowledge base maintained by Claude Code. Based on Andrej Karpathy's LLM Wiki pattern.

## Purpose

This wiki is a structured, interlinked knowledge base for organizing up-to-date medical and biological knowledge, and for tracking personal health data and protocols.

Claude maintains the wiki. The human curates sources, asks questions, and guides the analysis.

## Folder structure

```
0. DONOTTOUCH        -- (immutable -- never modify these)
1. RAW/              -- source documents (immutable -- never modify these)
2. WIKI/
  concepts/       -- general medical/biological knowledge
                     (diseases, mechanisms, drugs, nutrients, etc.)
  personal/       -- personal health data, symptoms, lab results, history
  protocols/      -- things the user is practicing or considering
                     (diet, exercise, supplements, sleep, etc.)
  index.md        -- table of contents for the entire wiki
  log.md          -- append-only record of all operations
```

The concepts/personal/protocols split matters. General knowledge, personal data, and personal practices have different epistemic statuses and should not be mixed on a single page.

## Ingest workflow

When the user adds a new source to `raw/` and asks you to ingest it:

1. Read the full source document
2. For research papers, summarize in PICO form first (Population, Intervention, Comparison, Outcome) before free-form discussion
3. Discuss key takeaways with the user before writing anything
4. Create a summary page in `wiki/concepts/` (or the appropriate folder) named after the source
5. Create or update concept pages for each major idea or entity
6. Before creating a new page, search existing pages' `Aliases` field for synonyms. Medical terms have many aliases (e.g. "myocardial infarction" / "MI" / "heart attack") — do not create duplicate pages
7. Add wiki-links ([[page-name]]) to connect related pages
8. Update `2. WIKI/index.md` with new pages and one-line descriptions
9. Append an entry to `2. WIKI/log.md` with the date, source name, and what changed

A single source may touch 10-15 wiki pages. That is normal.

## Page format

Every wiki page should follow this structure:

```markdown
# Page Title

**Summary**: One to two sentences describing this page.

**Aliases**: Other names for this concept (synonyms, abbreviations,
             translations). Leave empty if none.

**Sources**: List of raw source files this page draws from.

**Source dates**: Publication dates of the sources (to judge recency).

**Last updated**: Date of most recent update to this page.

---

Main content goes here. Use clear headings and short paragraphs.

Link to related concepts using [[wiki-links]] throughout the text.

## Related pages

- [[related-concept-1]]
- [[related-concept-2]]
```

## Citation rules

- Every factual claim should reference its source file and evidence level
- Format: `(source: filename.pdf, evidence: <level>)`
- Evidence levels (roughly strongest to weakest):
    - `meta-analysis` / `systematic-review`
    - `RCT` (randomized controlled trial)
    - `cohort` / `case-control`
    - `cross-sectional` / `case-series`
    - `case-report`
    - `mechanistic` (animal, in-vitro, pathway reasoning)
    - `expert-opinion` / `guideline`
    - `preprint` (append to the above when not peer-reviewed, e.g. `RCT, preprint`)
- Include sample size and population when relevant: `(n=1,234, population: adults with T2DM)`
- For quantitative claims, include effect size and confidence interval when available: `HR 0.78 (95% CI 0.65–0.93)`
- If two sources disagree, note the contradiction explicitly and compare their evidence levels
- If a claim has no source, mark it `[needs verification]`

## Question answering

When the user asks a question:

1. Read `2. WIKI/index.md` first to find relevant pages
2. Read those pages and synthesize an answer
3. Cite specific wiki pages in your response
4. If the answer is not in the wiki, say so clearly
5. Offer to save the answer as a new wiki page **only when** the answer is well-supported by existing cited sources. Do not file back answers that rely on a single source, are mostly your own inference, or mix in knowledge outside the wiki without marking it as such.

Good answers should be filed back into the wiki so they compound over time — but only when they meet the bar above.

## Lint

When the user asks you to lint or audit the wiki:

- Check for contradictions between pages
- Find orphan pages (no inbound links from other pages)
- Identify concepts mentioned in pages that lack their own page
- Flag claims that may be outdated based on newer sources
- Flag pages that rely on a **single source** for load-bearing claims (no corroboration)
- Flag pages whose sources are all **more than 5 years old** in fast-moving areas
- Flag practice recommendations in `protocols/` that rest only on low-evidence sources (`case-report`, `expert-opinion`, `mechanistic`)
- Flag claims in `personal/` or `protocols/` that conflict with general knowledge in `concepts/`
- Check for likely duplicate pages (same concept under different aliases)
- Check that all pages follow the page format above
- Report findings as a numbered list with suggested fixes

## Rules

- Never modify anything in the `0. DONOTTOUCH/`,  `1. RAW/` folder
- Always update `2. WIKI/index.md` and `2. WIKI/log.md` after changes
- Keep page names lowercase with hyphens (e.g. `lp-a.md`, `vitamin-d.md`)
- Write in clear, plain language
- Preserve technical terms and their definitions — do not over-simplify medical terminology; link to a glossary page instead
- When uncertain, prefer `[needs verification]` over a confident guess