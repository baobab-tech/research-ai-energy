# Jina Reader Skill

`r.jina.ai` fetches a URL and returns clean markdown. It renders JavaScript and handles PDFs,
which removes the two main reasons `WebFetch` fails here.

`JINA_API_KEY` is in `.env`. The key raises rate limits; it does not change which sites are
reachable. Tested on ACM and MDPI: keyed and keyless requests returned byte-identical content.
For a multi-agent pass making many calls the rate limit is the binding constraint, so use the
key.

## Basic use

```bash
curl -s --max-time 60 "https://r.jina.ai/https://dl.acm.org/doi/10.1145/3724499" -o /tmp/paper.md
```

Prefix any URL with `https://r.jina.ai/`. No encoding needed.

With a key:

```bash
set -a; source /Users/olivier/DEV/research-ai-energy/.env; set +a
curl -s "https://r.jina.ai/$URL" -H "Authorization: Bearer $JINA_API_KEY" -o /tmp/paper.md
```

## What it unblocks

Tested against the publishers that blocked retrieval during the September 2026 pass:

| Publisher | Result |
|---|---|
| ACM Digital Library | **works**, full text |
| MDPI (`www.mdpi.com`) | **works**, full text |
| IEEE Xplore | partial, abstract and metadata |
| Oregon PUC and similar state agency PDFs | **works**, full text |
| Wiley (`onlinelibrary.wiley.com`) | blocked, Cloudflare interstitial, keyed and keyless |
| Elsevier (`sciencedirect.com`) | blocked, Cloudflare interstitial, keyed and keyless |
| `ferc.gov` | blocked |

State regulatory PDFs are worth trying first here: Oregon PUC Order 26-154, which previous
retrieval attempts could not reach, came back as 184 KB of searchable text.

ACM and MDPI are the significant ones. Both previously required a workaround:
`mdpi-res.com/d_attachment/...` for MDPI, and finding an arXiv version for ACM. Neither
workaround is needed now, and ACM papers without an arXiv version are reachable for the first
time.

Where the response begins `Title: Just a moment...` or mentions security verification, the fetch
failed. Do not retry in a loop and do not attempt to work around the check. Fall back to the
repository-copy route in `skills/metadata.md`.

## Useful headers

```bash
# Return the page as plain text rather than markdown
-H "x-respond-with: text"

# Include image alt text and captions (useful for figure-only numbers)
-H "x-with-images-summary: true"

# Wait for a selector before returning, for slow JS pages
-H "x-wait-for-selector: .article-body"

# Target a subtree instead of the whole page
-H "x-target-selector: main"

# Follow the PDF rather than the landing page
-H "x-engine: direct"
```

## PDFs

Handles them directly, which removes the `pdftotext` step for most sources:

```bash
curl -s "https://r.jina.ai/https://www.iea.org/reports/energy-and-ai" -o /tmp/iea.md
```

Table fidelity is lower than `pdftotext -layout`. For a document where the numbers live in
tables, such as an agency report or a corporate data index, prefer downloading the PDF and
running `pdftotext -layout` as described in `skills/primary-sources.md`. Use Jina when the
document is HTML, when the PDF link is hidden behind a JS landing page, or as a fast first look.

## Where this sits in the retrieval order

1. arXiv id from Semantic Scholar `externalIds` (`skills/metadata.md`)
2. Green repository copy from Unpaywall
3. **Jina Reader on the publisher URL**
4. `pdftotext -layout` on a downloaded PDF, for table-heavy documents
5. Publisher-specific routes in `skills/primary-sources.md`
6. If none works, record in the excerpt's Limitations what could not be checked

## What it does not do

It is a fetcher, not a search engine and not a verifier. It returns what the page says. Confirm
the record is the right one with Crossref before writing anything up, and read the retrieved text
rather than a summary of it.

`s.jina.ai` offers search. Untested here; `skills/serper.md` is the search route in use.
