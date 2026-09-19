# Exa Skill

Key in `.env` as `EXA_API_KEY`.

**Use Exa for `/contents`, not for discovery.** Tested on this corpus in September 2026: neural
search for AI energy topics returned SEO blog content and no primary sources. Content extraction
on open pages returned clean full text and beat `WebFetch`.

## Content extraction

The reason to use Exa here. Returns parsed text from a URL, without the PDF-binary problem.

```bash
set -a; source /Users/olivier/DEV/research-ai-energy/.env; set +a

curl -s -X POST "https://api.exa.ai/contents" \
  -H "x-api-key: $EXA_API_KEY" -H "Content-Type: application/json" \
  -d '{"urls":["https://arxiv.org/abs/2508.15734"],"text":true}' \
  | jq -r '.results[0].text' > /tmp/paper.txt
```

Verified: 53,425 characters of clean text from an arXiv landing page.

Options worth knowing:

```json
{
  "urls": ["..."],
  "text": {"maxCharacters": 100000, "includeHtmlTags": false},
  "highlights": {"query": "energy per query", "numSentences": 3},
  "summary": {"query": "what system boundary does the water figure use?"}
}
```

`highlights` and `summary` are convenient but produce model output, not the source text. For
verification work, take `text` and read it. A summary of a paper is not evidence about the paper.

## What it will not do

It does not defeat publisher bot-blocking. Tested against a gold-OA Wiley paper: returned 0
characters. Unpaywall confirmed the paper is open but publisher-hosted with no PDF URL. No
content API solves that; see `skills/metadata.md` for the repository-copy route.

## Search

Available, and weak for this domain:

```bash
curl -s -X POST "https://api.exa.ai/search" \
  -H "x-api-key: $EXA_API_KEY" -H "Content-Type: application/json" \
  -d '{"query":"...","numResults":10,"type":"neural","startPublishedDate":"2026-01-01"}' \
  | jq -r '.results[] | "\(.publishedDate) | \(.title) | \(.url)"'
```

A September 2026 test query for measured per-query inference energy returned five results, all
SEO blog restatement, none primary. For this corpus that is worse than no result: secondary
restatement of a figure is how the original errors entered.

Use instead:

- **Serper** (`skills/serper.md`) aimed at named documents: "Ceres water behind the watts report",
  "ERCOT large load interconnection queue testimony"
- **OpenAlex** and **arXiv** (`skills/openalex.md`, `skills/arxiv.md`) for academic discovery
- **Semantic Scholar** (`skills/metadata.md`) for citation-graph traversal from a known paper

If Exa search is used at all, set `"category": "research paper"` and treat every result as a
lead to a primary document, never as a source.

## Domain filters

Where a specific publisher or agency is the target, constrain the search:

```json
{"includeDomains": ["iea.org", "eta-publications.lbl.gov", "eia.gov", "ferc.gov"]}
```

This is the one search mode worth using here: it behaves as a site-scoped fetch rather than a
topic search.
