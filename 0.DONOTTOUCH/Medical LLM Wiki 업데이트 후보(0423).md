# LLM Wiki

A personal knowledge base maintained by Claude Code. Based on Andrej Karpathy's LLM Wiki pattern.

## Purpose

This wiki is a structured, interlinked knowledge base for organizing up-to-date medical and biological knowledge, and for tracking personal health data and protocols.

Claude maintains the wiki. The human curates sources, asks questions, and guides the analysis.

## Folder structure

```
0. DONOTTOUCH        -- (immutable -- never modify these)
1. RAW/              -- source documents (immutable -- never modify these)
   1.0. pending   -- Non-ingested source documents, ingest these
   1.1. ingested  -- Ingested source documents
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

## Core principle — Wiki-first, raw on-demand

**The wiki is the primary context. Raw sources are on-demand references.**

Never bulk-read `1. RAW/` during ingest or question answering. A well-maintained wiki should answer most questions without touching raw. Raw is consulted only when explicit triggers fire (see Coverage gaps below).

Token budget rule: a typical ingest touches `index.md` + one new source + 3–10 existing pages + 0–2 re-referenced raw files. If you find yourself reading more than that, pause and tell the user why.

## Tag palette

All index.md tags must be in `2. WIKI/tags.md`.

- **English only**, lowercase, hyphenated, #-prefixed
- Korean search surface lives in page `Aliases` fields — NOT in tags
- Before inventing a new tag, check tags.md for existing option
- When adding a new tag: add to tags.md with a one-line definition 
  (English term — optional Korean gloss for human readers only, 
  not machine-matched)
- Lint rule: flag pages using tags not in tags.md (drift detection)

## Ingest workflow

When the user adds a new source to `1. RAW/1.0. pending/` and asks you to ingest it:

1. Read `2. WIKI/index.md` (full)
2. Read the new source document (once)
3. For research papers, summarize in PICO form (Population, Intervention, Comparison, Outcome) before free-form discussion
4. **Discover relevant existing pages** (see "Relation discovery" below)
5. Read only the relevant existing pages (typically 3–10, not the whole wiki)
6. Discuss key takeaways with the user before writing
7. **Check for conflicts or caveat triggers** (see "Conflict resolution" below) — consult raw only when triggered
8. Create or update pages:
    - New summary page in the appropriate folder, named after the source
    - Update concept pages where the new source adds, refines, or contradicts
    - Before creating a new page, search existing pages' `Aliases` field for synonyms. Medical terms have many aliases (e.g. "myocardial infarction" / "MI" / "heart attack") — do not create duplicate pages
9. Add wiki-links (`[[page-name]]`) to connect related pages
10. Update `2. WIKI/index.md` — only entries for new/changed pages
11. Append an entry to `2. WIKI/log.md` with the date, source name, and what changed

A single source may touch 10–15 wiki pages. That is normal. What is NOT normal: re-reading the entire raw/ folder for "completeness."

## Relation discovery

Finding which existing pages relate to a new source is the most failure-prone step. index.md one-liners miss details hidden in page bodies (Gap 1 — see Coverage gaps). Use all three signals:

1. **Extract entities from the new source** — drugs, diseases, mechanisms, genes, nutrients, people, methods
2. **Match against index.md entries** — one-line summaries AND tags (see index format below)
3. **Match against pages' Aliases fields** — synonyms, abbreviations, translations
4. **Follow one hop** — for each candidate page found, read its `## Related pages` section. Add any linked pages that plausibly relate to the new source. This catches indirect connections the index misses.

Stop at one hop unless the user asks for deeper exploration. Two-hop expansion blows up the page set fast.

## Conflict resolution

When the new source appears to contradict or tension with an existing page, DO NOT update the page immediately. Apparent contradictions split into three cases, only one of which is a real contradiction:

1. **Read the raw source(s) cited by the existing page** — the specific files listed in its `Sources` field
2. **Determine which case applies:**
    - **True contradiction** — both sources address the same population/condition and give opposing answers. Flag on both pages. Note dates, evidence levels, sample sizes. Do not pick a winner unless evidence levels differ clearly.
    - **Summary loss** — the existing page omitted a nuance (subgroup, caveat, effect modifier) that is actually present in its raw source. This is NOT a contradiction. Update the existing page to include the missing nuance. Add the nuance to the page's `Caveats` field going forward.
    - **Scope difference** — sources address different populations, doses, conditions, or time frames. Mark as complementary, not conflicting. Link the pages.
3. **Only then update the wiki.**

This is the main reason to consult raw. Without it, summary loss gets misreported as contradiction and the wiki accumulates false conflicts.

## Coverage gaps — know what you don't know

Summaries inherently lose information. Two gap points exist in this system:

### Gap 1 — Index → Wiki pages

`index.md` one-liners may not surface pages whose body contains relevant details. A page tagged "Lipoprotein(a), cardiovascular risk marker" won't obviously surface when the new source discusses Lp(a) and aortic valve calcification, even though the page body covers it.

**Mitigations:**

- Every index entry includes **tags** alongside the one-line summary (see index format below)
- Matching uses tags, one-liner text, AND each page's `Aliases` field
- After finding candidates, follow their `Related pages` one hop

### Gap 2 — Wiki page → Raw source

Wiki pages compress raw sources. Nuances (subgroup analyses, effect modifiers, caveats, unusual dose ranges, rare adverse events) often get cut to keep pages readable. New material may touch exactly what was cut — making the page look silent or wrong when the raw source actually has the answer.

**Mitigations:**

- Every page has a **`Caveats` field** declaring what it omits relative to its sources
- When new material touches a declared caveat topic → read the raw source cited
- When new material appears to contradict a page → Conflict resolution (always reads raw)

### Default bias

Trust the wiki. Escalate to raw only on explicit triggers:

| Situation                                                | Read raw? | Reason                       |
| -------------------------------------------------------- | --------- | ---------------------------- |
| New material aligns with existing page                   | ❌         | Unnecessary                  |
| New material touches a topic listed in page's `Caveats`  | ✅         | Required                     |
| Apparent contradiction (opposing numbers or conclusions) | ✅         | Required                     |
| Subtle nuance difference                                 | ❌         | Flag for user, don't dig yet |
| User explicitly requests deep re-verification            | ✅         | As requested                 |

## Index format

`2. WIKI/index.md` is a single file listing every wiki page. Format per entry:

```markdown
- [[lp-a]] — Lipoprotein(a), genetic cardiovascular risk marker
  tags: #lipid #genetic-risk #aortic-valve #inflammation #apo-a
```

The one-liner gives the human-readable summary. The tags give the machine-matchable surface area — every significant topic the page body covers, not just what's in the one-liner. If the page body discusses aortic valve calcification, `#aortic-valve` must be a tag even if the one-liner doesn't mention valves.

Tag hygiene:

- Lowercase, hyphenated, prefixed with `#`
- Reuse existing tags when possible (check other entries before inventing new ones)
- 3–10 tags per page is typical; more is fine for broad concept pages

Group entries by folder (concepts/, personal/, protocols/).

## Page format

Every wiki page follows this structure:

```markdown
# Page Title

**Summary**: One to two sentences describing this page.

**Aliases**: Other names for this concept (synonyms, abbreviations,
             translations). Leave empty if none.

**Sources**: List of raw source files this page draws from.

**Source dates**: Publication dates of the sources (to judge recency).

**Caveats**: Specific topics that the source materials DO cover but 
             this page simplifies, compresses, or omits. Do NOT list 
             topics outside the source's scope.

             - Format: single line, comma-separated topic list
             - Typical length: 2–10 items
             - Be specific ("pediatric dosing, CYP3A4 interactions, 
               long-term safety data"), not vague ("various dosing 
               concerns", "edge cases")
             - Topics that the source does not cover at all are NOT 
               caveats — they are simply out of scope
             - "None" is a strong claim — use only when the page 
               genuinely represents every significant point in its 
               sources; rare in practice
             

**Last updated**: Date of most recent update to this page.

---

Main content goes here. Use clear headings and short paragraphs.

Link to related concepts using [[wiki-links]] throughout the text.

## Related pages

- [[related-concept-1]]
- [[related-concept-2]]
```

The `Caveats` field is load-bearing. Fill it honestly when creating or updating a page. 

## Migration from pre-Caveats / pre-tag state

Existing pages created before this spec are in "not-yet-declared" state 
(no Caveats field, no index tags). Migration is opportunistic, not bulk:

- Do NOT mass-backfill Caveats or tags on untouched pages.
- When a page is CREATED or SUBSTANTIALLY UPDATED, fill Caveats and 
  index tags at the same time.
- When answering a question forces Claude to read a raw source for an 
  existing page, update that page's Caveats during the same session 
  (marginal cost is near zero when raw is already open).
- Default behavior for not-yet-declared pages: Gap 2 trigger defaults 
  ON — any new material on the page's topic triggers raw consultation.
  This compensates for the missing Caveats field.
- Untouched pages stay in not-yet-declared state. This is expected 
  and safe.

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
- If two sources disagree, note the contradiction explicitly and compare their evidence levels (after running Conflict resolution to confirm it's a true contradiction)
- If a claim has no source, mark it `[needs verification]`

## Internet Research - Source priority (highest to lowest):
Tier A = peer-reviewed literature, major institutional guidelines. Citable, filable to wiki. 
Tier B = blogs, forums, content farms. Single-use only, never filed.

- Primary literature: PubMed, journal sites (NEJM, Lancet, JAMA, Nature, Science)
- Institutional: NIH, CDC, FDA, WHO, major academic medical centers
  (Mayo Clinic, Cleveland Clinic, Johns Hopkins, 대한의학회, 주요 학회)
- Clinical references: UpToDate, StatPearls, Cochrane
- Avoid: personal blogs, promotional sites, content farms, 
  unverified Korean health blogs

## Question answering

When the user asks a question:

1. Read `2. WIKI/index.md` first to find relevant pages (match on one-liners AND tags)
2. Read those pages and synthesize an answer
3. Cite specific wiki pages in your response
4. If a cited page's `Caveats` field lists the user's question topic → read the raw source before answering
5. If there is not enough information in the raw source for a high-quality 
   answer, do targeted web research.
   - Escalate specifically for: quantitative figures (efficacy %, HR, NNT), 
     drug interactions, current approval/guideline status, post-cutoff events.
   - Prefer 1–2 targeted queries over broad exploration.
   - Citation format:
     - Papers: `(source: Author YYYY, Journal, PMID/DOI, evidence: <level>)`
     - Institutional: `(source: URL, accessed: YYYY-MM-DD, evidence: guideline)`
6. If the answer is not in the wiki and cannot be verified with high-quality 
   web sources, say so clearly. Do not fill the gap with low-quality sources.
7. Offer to save the answer as a new wiki page only when:
   - The answer is supported by multiple sources (wiki, raw, or peer-reviewed 
     papers found via web), AND
   - Web sources used are peer-reviewed literature or major institutional 
     guidelines (Tier A). Blog/forum/content-farm answers (Tier B) are for 
     single-use only and never filed back.
   - For web-sourced pages, cite the primary literature (not the URL alone); 
     these pages effectively stand in for PDFs-to-be-added-later to 1. RAW/.

Good answers should be filed back into the wiki so they compound over time — but only when they meet the bar above.


## Lint

When the user asks you to lint or audit the wiki:

- Check for contradictions between pages (run Conflict resolution on each to sort true contradictions from summary loss)
- Find orphan pages (no inbound links from other pages)
- Identify concepts mentioned in pages that lack their own page
- Flag claims that may be outdated based on newer sources
- Flag pages that rely on a **single source** for load-bearing claims (no corroboration)
- Flag pages whose sources are all **more than 5 years old** in fast-moving areas
- Flag practice recommendations in `protocols/` that rest only on low-evidence sources (`case-report`, `expert-opinion`, `mechanistic`)
- Flag claims in `personal/` or `protocols/` that conflict with general knowledge in `concepts/`
- Check for likely duplicate pages (same concept under different aliases)
- **Flag pages missing the `Caveats` field** or whose `Caveats` says "None" but draw from dense sources (possible honesty gap)
- **Flag index.md entries missing tags** or with fewer than 3 tags on broad concept pages
- Check that all pages follow the page format above
- Report findings as a numbered list with suggested fixes

## Rules

- Never modify anything in the `0. DONOTTOUCH/`,  `1. RAW/` folder
- On ingest request, scan only `1. RAW/1.0. pending/`.
- After ingest is complete and user has moved the file to `1. RAW/1.1. ingested/`, 
  log.md records the move.
- Before ingesting a new file, check log.md for filename match 
  (guards against user forgetting to move after previous ingest).
- Never auto-move files from pending to ingested. User owns the move.
- Always update `2. WIKI/index.md` and `2. WIKI/log.md` after changes
- Keep page names lowercase with hyphens (e.g. `lp-a.md`, `vitamin-d.md`)
- Write in clear, plain language
- Preserve technical terms and their definitions — do not over-simplify medical terminology; link to a glossary page instead
- When uncertain, prefer `[needs verification]` over a confident guess
- Trust the wiki by default; escalate to raw only on explicit triggers