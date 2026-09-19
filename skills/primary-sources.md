# Primary Sources Skill

Agency reports, grid-operator data, regulatory filings, and corporate disclosures hold the
defensible numbers. Most are PDFs and need extraction before they are readable.

## PDF extraction

`WebFetch` returns unparsed binary for PDFs. Download and convert first:

```bash
curl -sL "https://example.org/report.pdf" -o /tmp/r.pdf
pdftotext -layout /tmp/r.pdf - | less          # -layout preserves table columns
pdftotext -layout -f 12 -l 30 /tmp/r.pdf -     # page range only
```

Without `-layout`, table columns interleave and numbers bind to the wrong row.

## Where the numbers live

| Source | Holds | Access |
|--------|-------|--------|
| LBNL / Berkeley Lab | US data-centre TWh, share of national load, scenarios to 2030 | eta.lbl.gov, PDF |
| IEA | Global data-centre electricity, scenarios, avoided-emissions claims | iea.org/reports, PDF + some xlsx |
| EIA | US generation, demand, Short-Term Energy Outlook | eia.gov/opendata, JSON API, free key |
| ERCOT / PJM / MISO | Interconnection queues, large-load requests, capacity auctions, load forecasts | operator sites, PDF + xlsx |
| CSO Ireland | Metered data-centre consumption, the only national metered series | cso.ie, HTML tables |
| FERC / state PUCs | Tariff filings, co-location dockets, cost allocation | elibrary.ferc.gov, state docket portals |
| EU data-centre database | Article 12 EED reporting | ec.europa.eu |
| EPA | Facility emissions, permits (FLIGHT, ECHO) | epa.gov, queryable |
| Corporate | Scope 1/2/3, water withdrawal and consumption, PPAs | company sustainability report PDFs |

## Reading grid-operator queue data

An interconnection request measures intent. Capacity arrives at the end of this chain:

    requested -> studied -> agreement signed -> under construction -> energised

Attrition is severe at each step and operators publish the stages separately. State which stage a
figure refers to. Historically under one in five queued US projects reaches operation.

## Reading corporate disclosures

- Find both market-based and location-based Scope 2. The gap carries the claim.
- Water: distinguish withdrawal from consumption. Reports often give one only.
- Check whether "renewable" means unbundled RECs, annual-matched PPAs, or hourly-matched supply.
- Note the reporting boundary: which subsidiaries, which regions, leased and owned facilities.
- Check the restatement note. Prior-year figures are frequently revised without prominence.

## Superseded claims

Use the Wayback Machine (`skills/archive.md`) on sustainability pages. A pledge that was revised
or removed is a finding. Record the snapshot timestamp and quote both versions.
