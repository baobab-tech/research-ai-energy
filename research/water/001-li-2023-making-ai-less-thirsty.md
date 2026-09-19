# GPT-3 Training Consumes 5.44 Million Litres Total, of Which 0.71 Million Is On-Site Cooling Evaporation

**Topic:** Water — per-model and per-query water footprint of LLMs; scope-1 (on-site cooling) versus scope-2 (electricity generation) accounting
**Source:** Pengfei Li, Jianyi Yang (UC Riverside), Mohammad A. Islam (UT Arlington), Shaolei Ren (UC Riverside), 2023
**Type:** preprint (arXiv; v1 2023-04-06, current v5 2025-03-26)
**URL:** https://arxiv.org/abs/2304.03271
**Published:** 2023-04 (v5 revision 2025-03)

## Finding

The widely quoted "700,000 litres to train GPT-3" is the scope-1 term only: freshwater evaporated inside Microsoft's US data centres for cooling. The paper's own total for the same training run is 5.44 million litres, because scope-2 water consumed at the power plants generating the electricity adds 4.73 million litres, 87% of the total. The same split governs the per-query figure: a medium-length GPT-3 request consumes 2.2 mL on-site and 14.7 mL off-site on US-average assumptions, 16.9 mL in total, which is where the "500 mL bottle per roughly 10 to 50 responses" statement comes from. Every number is modelled from published PUE, WUE and grid-mix values, not measured; the authors apply no measurement of their own to any data centre.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| GPT-3 training, on-site water | 0.708 million L | Scope 1, evaporative cooling only; modelled as 1287 MWh × PUE 1.170 × WUE 0.550 L/kWh, Microsoft US fleet average |
| GPT-3 training, off-site water | 4.731 million L | Scope 2, electricity generation; EWIF 3.142 L/kWh, US average |
| GPT-3 training, total water | 5.439 million L | Scope 1 + 2; scope 3 (chip and server manufacture) excluded for lack of data |
| GPT-3 training energy | 1287 MWh | Taken from Patterson et al.; excludes hyperparameter tuning and failed runs |
| Per medium request, on-site | 2.200 mL | Scope 1, US average; assumed 0.004 kWh server energy per request |
| Per medium request, off-site | 14.704 mL | Scope 2, US average |
| Per medium request, total | 16.904 mL | Scope 1 + 2, US average |
| Requests per 500 mL bottle | 29.6 | US average, total-water basis |
| Range across 18 Microsoft locations, total per request | 7.107 mL (Ireland) to 47.506 mL (Washington) | Scope 1 + 2; spread driven by both on-site WUE and grid EWIF |
| Range across 18 locations, on-site per request | 0.000 mL (India) to 7.600 mL (Indonesia) | Scope 1 alone |
| Microsoft on-site WUE range used | 0.000 to 1.900 L/kWh | Self-reported annualised averages by location; asterisked sites are projections for facilities under construction as of July 2023 |
| Data centre evaporation, industry range | 1 to 9 L per kWh server energy | 1 L/kWh = Google annualised global; 9 L/kWh = a large commercial data centre, Arizona summer |
| Share of withdrawal that is evaporated | ~80% (cooling towers), ~70% (evaporation-assisted air cooling) | Google and Meta reported figures |
| Cooling tower water cycles before discharge | 3 to 10 | Depends on water quality |

A medium request is defined as approximately 800 words or fewer of input and 150 to 300 words of output.

## Methodology

Operational water = sum over time of (energy × [on-site WUE + PUE × off-site EWIF]). On-site WUE is scope-1 litres per kWh of server energy; off-site EWIF is litres per kWh of purchased electricity, computed as a fuel-mix-weighted average of per-fuel water intensities. Training energy for GPT-3 (1287 MWh) is taken from prior published work. PUE and WUE come from Microsoft's per-location disclosures; EWIF comes from Siddik, Shehabi and Marston (2021) for consistency of method across regions. Singapore and Taiwan are excluded because that source lacks EWIF for them. The specific data centre used to train GPT-3 is not public, so the paper reports 18 candidate locations rather than one answer.

Per-request energy of 0.004 kWh is derived from OpenAI's published figure of roughly 0.4 kWh per 100 pages of generated content, which the authors note likely counts GPU energy during token generation only. They state the inference estimate is conservative and cite DynamoLLM measurements of 0.010 kWh per medium request for Llama-3-70B and 0.016 kWh for Falcon-180B as evidence that the true figure could be several times higher.

Scope-2 numbers are location-based, not market-based: renewable purchase agreements would lower a market-based figure but do not change the water actually consumed at generating plants. Scope-3 embodied water is defined in the methodology but not quantified.

## Limitations and conflicts

Funded by NSF (CCF-2324916 to Li and Ren; ECCS-2152357 and CCF-2324915 to Islam). All authors are academic; no industry funding or affiliation is declared.

Nothing here is measured. The chain runs from a third-party training-energy estimate, through self-reported and in several cases projected corporate PUE and WUE values, to a literature EWIF. The 0.004 kWh per-request assumption is the weakest link and is acknowledged as such. The 700,000 L figure attaches to Microsoft's US fleet average, which the authors state is among the lowest on-site WUE in the industry, so a colocation deployment would be several times higher. The US EWIF used (3.142 L/kWh) is lower than the 4.35 L/kWh in the 2024 LBNL data centre report and lower than Meta's self-reported 3.70 L/kWh, biasing the scope-2 term downward. Water discharged and returned is not consumption, so withdrawal figures are substantially larger than the consumption figures reported here.

## Relation to existing corpus

The peer-reviewed version of this work is `research/water/018-li-2025-cacm-ai-water-projections.md` (CACM 68(7), 2025), which carries the same numbers and the global 2027 projection; the derivation appendix for that projection appears only in the arXiv version.

The 2.2 mL on-site figure is the like-for-like comparison against Google's 0.26 mL per median Gemini prompt in `research/water/017-google-2025-gemini-water-measurements.md`, since both are scope-1 cooling water. The 16.9 mL total is not comparable to 0.26 mL. `research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md` quantifies this: putting Google's figure on a boundary-complete basis gives 0.725 mL, and a long Gemini prompt reaches 28 mL, inside the range implied here.

---
Retrieved: 2026-09-19
Search: arXiv PDF https://arxiv.org/pdf/2304.03271v5 (and v1 for the original wording), full text via pdftotext
