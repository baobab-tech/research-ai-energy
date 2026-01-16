# Claude Instructions

This is a **research repository**, not a coding project.

## What We Do Here

- Search for academic papers, reports, and articles
- Extract insights and key findings
- Write markdown files with sources
- Aggregate research into topic summaries

## What We Don't Do

- Write code
- Build applications
- Create scripts (except simple curl commands for searching)

## Tools

Use curl commands from `/skills/` to search:
- **OpenAlex** - Academic papers (primary source)
- **arXiv** - Preprints
- **Serper** - Web, news, Google Scholar
- **Archive** - Internet Archive

## Output

All output is markdown files in `/research/{topic}/`.

Each file = one insight from one source, always with URL.

## Key Rules

1. Every fact needs a source URL
2. Write insights, not summaries
3. Be critical - flag conflicts of interest
4. Focus on 2024-2026 sources
5. Prioritize academic papers over news

---

## Research Process

### Capturing Insights

When you find something relevant:

**Don't just copy the abstract.** Write an insight that explains:
- What does this source tell us about the specific question?
- What's the key number, claim, or finding?
- How does it relate to our research topic?

If you need more details, fetch the page for abstract/metadata.

### Excerpt Format

Each finding gets saved as a small markdown file:

```markdown
# [Brief descriptive title]

**Topic:** [which research area this relates to]
**Source:** [Author/Org, Year]
**URL:** [full URL - REQUIRED]

## Insight

[2-4 sentences explaining what this source tells us about the topic. Not a summary of the paper - an insight relevant to our research question.]

## Key Data

[Any specific numbers, with context]
- Stat 1
- Stat 2

## Quote (optional)

> "Relevant quote from the source"

---
Retrieved: [date]
```

### File Organization

```
/research/
  /ghg/
    _index.md                          # Summary index for this folder
    001-strubell-2019-training-costs.md
    002-patterson-2021-carbon-emissions.md
    ...
  /water/
    _index.md
    001-li-2023-water-footprint.md
    ...
```

Files are numbered for ordering. Use descriptive names: `NNN-author-year-topic.md`

### Index Files

Each research folder has an `_index.md` with a quick-reference summary of all excerpts. Update it when adding new excerpts.

**Format:**
```markdown
# [Topic] Index

| # | Source | Insight | Link |
|---|--------|---------|------|
| 001 | Author, Year | One-sentence key finding | [file](001-file.md) |
| 002 | Author, Year | One-sentence key finding | [file](002-file.md) |
```

### Example Workflow

```bash
# 1. Search OpenAlex for training emissions papers
curl -s "https://api.openalex.org/works?search=LLM+training+energy+emissions&filter=publication_year:2024-2025&sort=cited_by_count:desc&per_page=10" | jq '.results[] | {title, year: .publication_year, citations: .cited_by_count, doi}'

# 2. Find interesting result, fetch more details if needed
curl -s "https://api.openalex.org/works/doi:10.xxxx/xxxxx" | jq '{title, abstract_inverted_index, authorships}'

# 3. Write excerpt file with insight + URL
# 4. Save to /research/ghg/001-author-year-topic.md
```

### Critical Stance

Every excerpt should consider:
- **Source credibility**: Who wrote this? Who funded it?
- **Methodology**: How did they get these numbers?
- **Conflicts of interest**: Industry-funded? Self-reported data?
- **What's missing**: What don't they say?

Flag any concerns in the excerpt.

---

See `RESEARCH_PLAN.md` for research areas, search terms, and task definitions.
