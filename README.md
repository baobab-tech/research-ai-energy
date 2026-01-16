# AI Environmental Impact Research

Critical investigation into the environmental footprint of AI systems: greenhouse gas emissions, water consumption, and the gap between corporate claims and reality.

## Research Process

### How It Works

1. **Search** - Query OpenAlex, arXiv, or Serper for a specific topic
2. **Find** - Identify relevant papers, articles, reports
3. **Extract** - Write an insight (not just the abstract - how does it relate to the topic?)
4. **Store** - Save as individual excerpt file with source URL
5. **Aggregate** - Later, combine excerpts into topic summaries

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
  /washing/
    _index.md
    001-greenpeace-2024-tech-claims.md
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

This makes it easy to scan what's been captured without opening each file.

### Search Tools

See `/skills/` for curl commands:
- `openalex.md` - Academic papers (primary)
- `arxiv.md` - Preprints
- `serper.md` - Web, news, Google Scholar
- `archive.md` - Internet Archive, Wayback

### Example Workflow

```bash
# 1. Search OpenAlex for training emissions papers
curl -s "https://api.openalex.org/works?search=LLM+training+energy+emissions&filter=publication_year:2024-2025&sort=cited_by_count:desc&per_page=10" | jq '.results[] | {title, year: .publication_year, citations: .cited_by_count, doi}'

# 2. Find interesting result, fetch more details if needed
curl -s "https://api.openalex.org/works/doi:10.xxxx/xxxxx" | jq '{title, abstract_inverted_index, authorships}'

# 3. Write excerpt file with insight + URL
# 4. Save to /research/ghg/001-author-year-topic.md
```

## What We're Researching

See `RESEARCH_PLAN.md` for:
- Full list of research areas and sub-topics
- Key search terms
- Sub-agent task definitions
- Progress tracking

## Critical Stance

Every excerpt should consider:
- **Source credibility**: Who wrote this? Who funded it?
- **Methodology**: How did they get these numbers?
- **Conflicts of interest**: Industry-funded? Self-reported data?
- **What's missing**: What don't they say?

Flag any concerns in the excerpt.

## Rules

1. **Every fact needs a URL** - No exceptions
2. **Insights, not summaries** - How does it relate to our question?
3. **Note methodology** - Especially for numbers/estimates
4. **Flag COI** - Note if industry-funded or self-reported
5. **Date everything** - Research landscape changes fast
