# Claude Instructions

A research repository. Output is markdown files under `/research/`.

**Updating this repository:** read [METHOD.md](METHOD.md) first. An update is audit, search,
verify, prune, rebuild. A pass that only adds new sources leaves the existing material wrong and
every summary built on it wrong; that has happened here and is documented in METHOD.md.

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

1. **Measurement.** Instrumented production systems, metered data, grid-operator telemetry.
2. **Agency and statutory data.** IEA, LBNL/Berkeley Lab, EIA, EPRI, JRC, EU data-centre database, PUC and FERC filings.
3. **Peer-reviewed papers and preprints.** OpenAlex, arXiv.
4. **Corporate disclosures.** Sustainability reports, 10-K climate sections, model cards. Primary evidence of what a company claims and how it accounts.
5. **Journalism**, used only to reach a document or dataset otherwise unavailable. Cite and characterise the underlying document; the article's framing carries no weight.

A corporate report evidences what the company claims. It does not evidence whether the claim holds.

## Hard rules

0. **Verify before citing.** A figure entering a README, a folder summary, or a reply to the user
   must come from a source retrieved in this pass, not from an existing excerpt. Excerpts have
   been wrong; propagating one without checking is how the error spreads.
1. **Every fact carries a URL that was actually retrieved.** Confirm it resolves.
1a. **Confirm the record before writing.** Check the DOI against Crossref: if the returned title
   is not the paper, the DOI is wrong; if the author list does not match, the citation is wrong.
   Both have occurred here. One call, in `skills/metadata.md`.
2. **No abstract-only write-ups.** If the finding cannot be established from the full text, PDF, or OA copy, skip the source. Banned phrasings: "likely addresses", "presumably", "full paper needed", "implies the authors argue".
3. **Numbers carry units, system boundary, and method.** "0.24 Wh per prompt" is incomplete until the boundary is stated as accelerator-only, full-stack, or PUE-inclusive, and the statistic as median or mean.
4. **Name the epistemic status.** Measurement, estimate, projection, and model output are different things. Say which.
5. **One file per finding, not one file per topic.** Before writing, `grep -ril "<author>" research/`. If the source is already held, extend that file or cross-link it. Writing the same finding up again in a second folder is the failure mode: five copies of one paper here made five different and partly invented claims about it. A large document (an agency report, a corporate environmental report) may legitimately support separate files in separate folders when each carries a genuinely different finding. Say so in `Relation to existing corpus`, naming the other file and what it covers.
6. **On topic.** Each excerpt bears directly on AI or data-centre energy, water, emissions, grid, siting, or the claims made about them. General ESG theory, municipal water engineering, and corporate-governance econometrics belong elsewhere.
7. **Record funding and affiliation** on every excerpt, including when there is no apparent conflict.
8. **The number must be in the source.** A figure derived by arithmetic on the source's prose is
   an estimate and is labelled as one. See `skills/verification.md` for the failure modes this
   rule exists to prevent.
9. **`DELETE` is a valid outcome.** An excerpt that misdescribes its source is worse than no
   excerpt. Relevance the source does not claim is not relevance.

## Distinctions

Conflating either side of these pairs is the most common error in this literature, and the most
common cause of an apparent disagreement that is not one. Before reporting two figures as in
conflict, establish that they share a boundary:

- **Water withdrawal against water consumption.** Withdrawn water may return to the basin; consumed water does not.
- **On-site against off-site water.** Cooling evaporation, against water embedded in electricity generated elsewhere.
- **Market-based against location-based Scope 2.** The gap between them carries the "carbon neutral" claim.
- **Announced, under construction, and energised capacity.** Reported interchangeably; they differ by years and by gigawatts.
- **Contracted against delivering generation.** A signed nuclear PPA supplies no electrons.
- **Efficiency per token against absolute consumption.** Both move in opposite directions at once.

## Excerpt format

Path: `/research/<topic>/NNN-author-year-topic.md`

```markdown
# [Title stating the finding]

**Topic:** [area + sub-question]
**Source:** [Author(s)/Organisation, Year]
**Type:** [peer-reviewed | preprint | agency report | corporate disclosure | dataset]
**URL:** [verified]
**Published:** [YYYY-MM]

## Finding

[2-4 sentences on what this source establishes.]

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

## State, not changelog

Files describe the current state of the evidence. No `supersedes`, `corrected`,
`previously stated`, or `correction needed` annotations anywhere in `/research/`. When an excerpt
is wrong, write the right thing: git history records the change and the commit message names it.

`Relation to existing corpus` is for relationships between different sources, not for narrating
edits. Report corrections to the user in conversation.

## Writing style

- Lead with the finding. State it once.
- Declarative. No verdict words: interesting, important, key, striking, alarming, powerful.
- No sentences about the document: "this section covers", "as noted above".
- Report uncertainty as ranges with the assumptions that produce them.
- Attribute contested claims to whoever made them. Do not adopt their framing.
- Where a claim is well-evidenced, record that it is. The aim is to separate substantiated claims from unsubstantiated ones.

## Critical stance

Applied to every source, including ones whose conclusions are congenial:

- Who funded it, who employs the authors
- What the system boundary excludes
- Self-reported or independently verified
- What a reader would want that the source does not give

Apply the same scrutiny to critical research as to industry research. A study finding large AI impacts deserves the same methodological interrogation as one finding small impacts.

## Files that describe a folder

Each `/research/<topic>/` carries two of these, and both need updating when excerpts are added.

**`README.md`** is the folder's summary, and GitHub renders it on the folder landing page. It holds:

- One or two lines naming what the folder covers and how many excerpts it holds
- A link to `_index.md`
- The established figures as a table, each with its system boundary and a link to the excerpt
- How to read those numbers: what the boundary excludes, which figures are inferred, where two sources disagree and why
- Corrections held in the folder, naming the superseded file
- Gaps, stated as what no source establishes

Keep it to what a reader needs before opening any excerpt. It summarises; it does not restate the index table.

**`_index.md`** is the scannable table of every excerpt, one row each, with the source name linked to its file. Do not renumber existing rows.

`/research/_log.md` records searches performed, including those that returned nothing. Negative results mark where evidence does not yet exist.

## Tools

| File | Holds |
|------|-------|
| `skills/openalex.md`, `skills/arxiv.md` | academic search, no key needed |
| `skills/openalex-api-reference.md`, `skills/arxiv-api-reference.md` | full API field and filter references |
| `skills/jina.md` | fetch a URL as clean markdown; reaches ACM, MDPI and state agency PDFs |
| `skills/serper.md` | web, news and scholar search; key in `.env` (gitignored) |
| `skills/archive.md` | Wayback Machine, for revised or removed corporate pages |
| `skills/primary-sources.md` | agency, grid-operator and corporate documents; PDF extraction; publisher blocks |
| `skills/metadata.md` | Crossref, Semantic Scholar, Unpaywall; identity and full-text routes |
| `skills/exa.md` | content extraction from open pages; not for discovery |
| `skills/verification.md` | failure modes, the check suite, shell gotchas |

Use the Internet Archive for corporate sustainability pages that have been revised or removed. Superseded claims are evidence.

## Where things are

| File | Purpose |
|------|---------|
| `METHOD.md` | how to run an update, phase by phase |
| `RESEARCH_PLAN.md` | research areas and open questions |
| `skills/verification.md` | failure modes and the pre-commit check suite |
| `research/<topic>/README.md` | folder summary: figures, boundaries, gaps |
| `research/<topic>/_index.md` | one row per excerpt |
| `research/_log.md` | searches run, including those that found nothing |
| `research/_queue.md` | current state and what is next |
