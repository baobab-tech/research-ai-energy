# Claude Instructions

This is a research repository, not a coding project. Output is markdown files under `/research/`.

## What happens here

- Search for papers, agency reports, regulatory filings, and corporate disclosures
- Extract findings with their numbers, units, and system boundaries
- Write one markdown file per source, always with a retrieved URL
- Maintain a per-topic index and a search log

## What does not happen here

- Writing code or building applications
- Scripts beyond curl and jq for querying APIs

## Source hierarchy

Ranked by evidentiary weight for a question about numbers:

1. **Measurement** — instrumented production systems, metered data, grid-operator telemetry
2. **Agency and statutory data** — IEA, LBNL/Berkeley Lab, EIA, EPRI, JRC, EU data-centre database, PUC and FERC filings
3. **Peer-reviewed papers and preprints** — OpenAlex, arXiv
4. **Corporate disclosures** — sustainability reports, 10-K climate sections, model cards. Primary evidence about what a company claims and how it accounts. Never a neutral fact.
5. **Journalism** — only to reach a document or dataset otherwise unavailable. Cite and characterise the underlying document, not the article's framing.

A corporate report is a primary source about the company's own claims. It is not a source for whether the claim is true.

## Hard rules

1. **Every fact carries a URL that was actually retrieved.** Confirm it resolves.
2. **No abstract-only write-ups.** If the finding cannot be established from the full text, PDF, or OA copy, skip the source. Banned: "likely addresses", "presumably", "full paper needed", "implies the authors argue".
3. **Numbers carry units, system boundary, and method.** "0.24 Wh per prompt" is incomplete without knowing accelerator-only versus full-stack versus PUE-inclusive, and median versus mean.
4. **Name the epistemic status.** Measurement, estimate, projection, and model output are different things. Say which.
5. **One canonical file per source.** Before writing, `grep -ril "<author>" research/`. If the source is held, extend the existing file or cross-link it from the other index. Do not write it up again.
6. **On topic.** Must bear directly on AI or data-centre energy, water, emissions, grid, siting, or the claims made about them. General ESG theory, municipal water engineering, and corporate-governance econometrics do not belong here.
7. **Record funding and affiliation** on every excerpt, including when there is no apparent conflict.

## Distinctions that decide arguments

Getting these wrong is how this literature goes astray:

- **Water withdrawal vs water consumption** — withdrawn water may return to the basin; consumed water does not
- **On-site vs off-site water** — cooling evaporation versus water embedded in the electricity generated elsewhere
- **Market-based vs location-based Scope 2** — the gap between them is where "carbon neutral" claims live
- **Announced vs under construction vs energised** capacity — usually reported interchangeably, differ by years and by gigawatts
- **Contracted vs delivering** generation — a signed nuclear PPA is not electrons on the grid
- **Efficiency per token vs absolute consumption** — both can move in opposite directions at once

## Excerpt format

Path: `/research/<topic>/NNN-author-year-topic.md`

```markdown
# [Title stating the finding, not the subject]

**Topic:** [area + sub-question]
**Source:** [Author(s)/Organisation, Year]
**Type:** [peer-reviewed | preprint | agency report | corporate disclosure | dataset]
**URL:** [verified]
**Published:** [YYYY-MM]

## Finding

[2-4 sentences on what this source establishes. Not an abstract summary.]

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|

## Methodology

[How the numbers were produced. What is measured, modelled, or assumed.]

## Limitations and conflicts

[Funding, affiliation, self-reporting, omissions, where the estimate is weakest.]

## Relation to existing corpus

[Confirms, contradicts, or supersedes which file. "No direct overlap" if none.]

---
Retrieved: YYYY-MM-DD
Search: [exact query and source]
```

## Writing style

- Lead with the finding. State it once.
- Declarative. No verdict words: interesting, important, key, striking, alarming, powerful.
- No sentences about the document: "this section covers", "as noted above".
- Report uncertainty as ranges with the assumptions that produce them.
- Attribute contested claims to whoever made them. Do not adopt their framing.
- Where a claim is well-evidenced, record that it is. The aim is to separate substantiated from unsubstantiated, not to reach a predetermined verdict.

## Critical stance

Applied to every source, including ones whose conclusions are congenial:

- Who funded it, who employs the authors
- What the system boundary excludes
- Self-reported or independently verified
- What a reader would want that the source does not give

Apply the same scrutiny to critical research as to industry research. A study finding large AI impacts deserves the same methodological interrogation as one finding small impacts.

## Index and log

Each `/research/<topic>/_index.md` holds a scannable table of that folder's excerpts. Update it when adding files; do not renumber existing rows.

`/research/_log.md` records searches performed, including those that returned nothing — negative results mark where evidence does not yet exist.

## Tools

Query templates in `/skills/`: `openalex.md`, `arxiv.md`, `serper.md`, `archive.md`. Serper key in `.env` (gitignored). OpenAlex and arXiv need no key.

Use the Internet Archive for corporate sustainability pages that have been revised or removed — superseded claims are evidence.

See `RESEARCH_PLAN.md` for research areas and open questions.
