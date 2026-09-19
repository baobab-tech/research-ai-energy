# Global AI Projected to Withdraw 4.2 to 6.6 Billion Cubic Metres of Water in 2027, of Which 0.38 to 0.60 Billion Is Consumed

**Topic:** Water — global AI water demand projection to 2027; withdrawal versus consumption, scope-1 versus scope-2
**Source:** Pengfei Li, Jianyi Yang (UC Riverside), Mohammad A. Islam (UT Arlington), Shaolei Ren (UC Riverside), 2025
**Type:** peer-reviewed (Communications of the ACM 68(7), 54-61)
**URL:** https://doi.org/10.1145/3724499
**Source note:** dl.acm.org blocks automated requests; author copy at https://crystal.uta.edu/~mislam/pdfs/2025_CACM.pdf
**Published:** 2025-06

## Finding

The 4.2 to 6.6 billion cubic metre headline is water *withdrawal*, not consumption, and 98% of it is scope-2 water at power plants rather than water evaporated in data centres. Consumption, the quantity that removes water from a watershed, is 0.38 to 0.60 billion cubic metres, an order of magnitude smaller. The projection is arithmetic on one input: de Vries's estimate that global AI consumes 85 to 134 TWh in 2027, grossed up by PUE 1.1 to 93.5 to 147.4 TWh, then multiplied by fixed national-average water intensity factors. The Denmark and UK comparisons are withdrawal-to-withdrawal and hold only if those countries' 2020 withdrawals persist to 2027.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Global AI water withdrawal, 2027 | 4.2 to 6.6 billion m³ | Scope 1 + 2, projected; withdrawal, not consumption |
| Global AI water consumption, 2027 | 0.38 to 0.60 billion m³ | Scope 1 + 2, projected; evaporated or otherwise removed |
| Scope-1 (data centre) withdrawal | 0.11 to 0.16 billion m³ | On-site cooling; assumed 1.2 L/kWh, from Google and Equinix disclosures |
| Scope-1 consumption | 0.09 to 0.14 billion m³ | On-site cooling; assumed 1.0 L/kWh |
| Scope-2 (generation) withdrawal | 4.10 to 6.46 billion m³ | Electricity generation; EWIF 43.83 L/kWh (US average, EIA) |
| Scope-2 consumption | 0.29 to 0.46 billion m³ | Electricity generation; EWIF 3.14 L/kWh (US average) |
| Input AI electricity, 2027 | 85 to 134 TWh (server) → 93.5 to 147.4 TWh (facility) | Third-party projection, grossed up by assumed PUE 1.1 |
| Denmark annual withdrawal, 2020 | 0.98 billion m³ | CIA World Factbook; basis of the "4 to 6 Denmarks" comparison |
| UK annual withdrawal, 2020 | 8.42 billion m³ | Same source; basis of the "half the UK" comparison |
| GPT-3 training, total water | 5.439 million L (0.708 on-site, 4.731 off-site) | Scope 1 + 2, modelled, Microsoft US fleet average |
| GPT-3 per medium request | 16.904 mL total (2.200 on-site, 14.704 off-site) | Scope 1 + 2, US average, 0.004 kWh assumed per request |
| Requests per 500 mL bottle | 29.6 (US average); stated range 10 to 50 across locations | Total-water basis |
| One company's 2023 self-owned data centre water | 29 billion L withdrawn, >23 billion L consumed, ~80% potable | Scope 1 only, excludes leased colocation; from Google's environmental report |
| US data centre on-site water consumption, 2028 | 150 to 280 billion L | Scope 1, projected; from the 2024 LBNL data centre report, not computed here |

## Methodology

Scope-1: assumed global fleet efficiencies of 1.2 L/kWh withdrawal and 1.0 L/kWh consumption, taken from Google (hyperscale) and Equinix (colocation) annual reports, applied to the projected AI electricity total.

Scope-2: US national-average electricity water intensity factors applied to global AI electricity. Withdrawal uses 43.83 L/kWh from EIA; consumption uses 3.14 L/kWh from Siddik, Shehabi and Marston (2021). The authors note that the latter source, which includes hydropower, would give 386.07 L/kWh for withdrawal, and they deliberately use the lower EIA figure instead.

The authors characterise the estimate as conservative on four counts: US intensity factors are below global averages, 3.14 L/kWh is below the 4.35 L/kWh in the 2024 LBNL report and below Meta's self-reported 3.70 L/kWh, PUE 1.1 is low even for state-of-the-art facilities, and the lower of two available AI electricity projections was used. They observe that on the LBNL projection, US AI alone could reach about 2 billion m³ of combined scope-1 and scope-2 consumption in 2028, above their global 2027 figure.

Content is otherwise identical to the arXiv version of the same work, with the derivation appendix omitted from the CACM text.

## Limitations and conflicts

Funded by NSF (CCF-2324916, ECCS-2152357, CCF-2324915). Academic authors only; no industry funding or affiliation declared.

The projection inherits all the uncertainty of the AI electricity forecast it multiplies, which is itself a scenario rather than a measurement. Applying US-average generation water intensities to global electricity is a stated simplification. The scope-1 term assumes fleet-wide water efficiency equal to two of the better-reporting operators, which understates colocation and non-hyperscale facilities. Withdrawal figures depend on whether hydropower is counted, and the paper's choice of the EIA convention over the alternative changes the scope-2 withdrawal result by roughly a factor of nine. Scope-3 water for chip and server manufacture is excluded throughout; Apple is cited as reporting that its supply chain accounts for 99% of its total water footprint.

## Relation to existing corpus

The arXiv version of this work is `research/water/001-li-2023-making-ai-less-thirsty.md`, which carries the appendix deriving the 2027 projection.

The per-query numbers here are what `research/water/017-google-2025-gemini-water-measurements.md` positions itself against. The comparison is boundary-mismatched: Google's 0.26 mL is scope-1 only, against 2.2 mL scope-1 here. `research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md` reconstructs Google's figure on a scope-1 + scope-2 basis at 0.725 mL and puts a long Gemini prompt at 28 mL.

---
Retrieved: 2026-09-19
Search: Crossref for DOI 10.1145/3724499 (CACM 68(7), 54-61); full text via author copy at crystal.uta.edu, cross-checked against arXiv 2304.03271v5 appendix
