# Metadata Skill

Verify a source's identity before writing about it. Crossref, Semantic Scholar and Unpaywall are
free and need no key. Running these three takes seconds and catches errors that survived for
months in this corpus.

## Mandatory check: confirm the record before writing an excerpt

```bash
DOI="10.1016/j.ijrefrig.2024.01.015"
curl -s "https://api.crossref.org/works/$DOI" | jq -r '.message | {
  title: .title[0],
  authors: [.author[]? | "\(.given) \(.family)"] | join("; "),
  container: .["container-title"][0],
  year: (.published["date-parts"][0][0]),
  volume, page, publisher
}'
```

If the returned title does not match the paper being written up, the DOI is wrong. This has
happened here: a guessed DOI returned a paper on methane condensation in minitubes.

If the returned author list does not match the excerpt's `**Source:**` line, the citation is
wrong. This has also happened here: one excerpt named an author's *first* name as the lead
surname, producing an author list that matches no publication.

## Find a legal full-text copy

### Unpaywall: DOI to open-access location

```bash
curl -s "https://api.unpaywall.org/v2/$DOI?email=YOUR_EMAIL" | jq -r '{
  is_oa, oa_status,
  pdf: .best_oa_location.url_for_pdf,
  landing: .best_oa_location.url_for_landing_page,
  host: .best_oa_location.host_type,
  repos: [.oa_locations[]? | select(.host_type=="repository") | .url_for_pdf]
}'
```

`oa_status` values: `gold` (publisher OA), `green` (repository copy), `hybrid`, `bronze`
(free to read, no licence), `closed`.

**`is_oa: true` does not mean retrievable.** A gold-OA paper hosted only on a publisher that
blocks automated requests returns `url_for_pdf: null`. When that happens, check the `repos`
array for a green copy in an institutional repository, which is usually not blocked.

### Semantic Scholar: OA PDF, plus authors and references

```bash
curl -s "https://api.semanticscholar.org/graph/v1/paper/DOI:$DOI?fields=title,year,authors,openAccessPdf,externalIds,citationCount,publicationVenue" | jq
```

`externalIds` often carries an `ArXiv` id even when the publisher version is paywalled, which is
the fastest route to full text. Also accepts `arXiv:2508.15734` and `CorpusID:` as lookup keys.

No key needed. A free key raises the rate limit if a pass is making many calls.

### Search when there is no DOI

```bash
curl -s -G "https://api.crossref.org/works" \
  --data-urlencode "query.bibliographic=Investigations on heat transfer enhancement data centre cooling" \
  --data-urlencode "rows=5" \
  | jq -r '.message.items[] | "\(.DOI) | \(.title[0]) | \([.author[]?|.family]|join(", "))"'
```

Use this to recover the correct DOI when an excerpt's citation looks wrong.

## Citation counts

Do not use them as evidence. They go stale, they vary by index, and they say nothing about
whether a claim is correct. Verified here: an excerpt claiming "578 citations, exceptionally
high" against a current Crossref figure of 1,361, and two counts dated before their paper was
published.

If a count is recorded at all, date it and name the index:

```bash
curl -s "https://api.semanticscholar.org/graph/v1/paper/DOI:$DOI?fields=citationCount" \
  | jq -r '"\(.citationCount) (Semantic Scholar, retrieved '"$(date +%F)"')"'
```

## One check, three calls

```bash
verify_doi() {
  local doi="$1" email="${2:-olivier@millsit.ca}"
  echo "--- Crossref ---"
  curl -s "https://api.crossref.org/works/$doi" | jq -r '.message | "\(.title[0])\n\([.author[]?|"\(.given) \(.family)"]|join("; "))\n\(.["container-title"][0]) \(.published["date-parts"][0][0])"'
  echo "--- Unpaywall ---"
  curl -s "https://api.unpaywall.org/v2/$doi?email=$email" | jq -r '"oa=\(.is_oa) status=\(.oa_status) pdf=\(.best_oa_location.url_for_pdf // "none")"'
  echo "--- Semantic Scholar ---"
  curl -s "https://api.semanticscholar.org/graph/v1/paper/DOI:$doi?fields=openAccessPdf,externalIds" | jq -r '"pdf=\(.openAccessPdf.url // "none") arxiv=\(.externalIds.ArXiv // "none")"'
}
```

## Retrieval order

1. `arXiv` id from Semantic Scholar `externalIds`, then `https://arxiv.org/pdf/<id>`
2. Green repository copy from Unpaywall `oa_locations`
3. PMC, for anything biomedical or health-adjacent
4. Publisher landing page, expecting a 403 from Elsevier, Wiley, IEEE, ACM and `www.mdpi.com`
5. Author's institutional page or personal site
6. If none works, say so in the excerpt's Limitations and mark what could not be checked

See `skills/primary-sources.md` for publisher-specific routes that do work, and for PDF text
extraction.
