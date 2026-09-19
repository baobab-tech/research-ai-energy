# US Midsize Data Centre WUE Rose from 0.52-0.86 to 0.56-0.96 L/kWh While PUE Fell, as Water-Cooled Chillers Spread

**Topic:** Water — WUE of non-hyperscale US data centres; the energy-efficiency versus water-intensity trade-off in cooling system choice
**Source:** Nuoa Lei, Mohan Ganeshalingam, Eric Masanet, Sarah Smith, Arman Shehabi (Lawrence Berkeley National Laboratory; Masanet also UC Santa Barbara), 2025
**Type:** peer-reviewed (Energy and Buildings 339, 115734)
**URL:** https://doi.org/10.1016/j.enbuild.2025.115734
**Source note:** Elsevier blocks automated requests; accepted version open at https://www.osti.gov/pages/servlets/purl/3398559
**Published:** 2025-07

## Finding

Midsize US data centres got more energy-efficient and more water-intensive at the same time between 2012 and 2018: PUE fell from 1.46-1.83 to 1.43-1.76 while WUE rose from 0.52-0.86 to 0.56-0.96 L/kWh. Small data centres moved the other way, holding PUE flat at roughly 1.82-2.28 while WUE fell from 0.26-0.42 to 0.21-0.35 L/kWh. The mechanism is cooling system market share, not equipment improvement: midsize facilities adopted water-cooled chillers and evaporative cooling, which trade water for electricity, while small facilities stayed on direct-expansion units that use almost no water and more power. Both PUE and WUE are estimated by weighting published per-cooling-system efficiency values by CBECS-derived market shares; neither is measured at any facility.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Small data centre WUE, 2012 | 0.26-0.42 L/kWh | On-site water per kWh of IT electricity; estimated by weighting per-cooling-system WUE by CBECS market share |
| Small data centre WUE, 2018 | 0.21-0.35 L/kWh | Same |
| Midsize data centre WUE, 2012 | 0.52-0.86 L/kWh | Same |
| Midsize data centre WUE, 2018 | 0.56-0.96 L/kWh | Same |
| Small data centre PUE, 2012 → 2018 | 1.82-2.29 → 1.82-2.28 | Same method |
| Midsize data centre PUE, 2012 → 2018 | 1.46-1.83 → 1.43-1.76 | Same method |
| Facility count, small and midsize | 1.764 million (2012) → 1.398 million (2018) | CBECS survey estimate; 21% decline |
| Server stock, small and midsize | 5.177 million (2012) → 4.262 million (2018) | Small 3.704 → 2.954; midsize 1.473 → 1.308 |
| Servers housed in office buildings | >40% of small data centre servers; 55% of midsize | CBECS building-type classification |
| Geographic concentration | Over half of servers in climate zones 5A (cold), 3A and 4A (mixed-humid) | CBECS plus OES-based geospatial allocation |
| Evaporative cooling market share | 0.2% → 5.2% | Share among small and midsize data centres, 2012 to 2018 |
| Dominant cooling system | Direct expansion units, throughout the period | With a clear shift toward air economizers |
| Comparison: hyperscale PUE | 1.16-1.28 (2023, LBNL) | Not estimated in this study |
| Comparison: AI data centre PUE | 1.09-1.19 (2023, LBNL) | Not estimated in this study |

The ranges are 5th to 95th percentile bands across cooling system types and climate zones, not confidence intervals on a measurement.

## Methodology

CBECS 2012 and 2018 microdata give counts of buildings with server rooms, server counts, building type and cooling system type. Server geospatial distribution is approximated by assuming a linear relationship between server counts and the number of workers in a building, using Occupational Employment Statistics. Aggregate PUE and WUE are computed as market-share-weighted averages of per-cooling-system, per-climate-zone PUE and WUE values published in the authors' own earlier work (Lei and Masanet 2020, 2022; Lei et al. 2023). The uncertainty bands come from within-cooling-type variation in equipment efficiency and operational settings.

Small and midsize data centres are the CBECS categories; hyperscale and dedicated AI facilities are outside the scope and are shown only as literature comparisons.

## Limitations and conflicts

Funded by the US Department of Energy, Office of Energy Efficiency and Renewable Energy, Industrial Efficiency and Decarbonization Office; LBNL operates under DOE contract DE-AC02-05CH11231. No industry funding or conflict declared. Published open access under CC BY.

The WUE numbers are engineering estimates layered on survey data, two steps removed from metered water. CBECS is a sample survey with its own sampling error, and the 2018 wave is the most recent available, so the series stops seven years before AI-driven cooling changes. The linear servers-per-worker assumption for geospatial allocation is acknowledged by the authors as inapplicable to large cloud and AI facilities. The underlying per-cooling-system WUE values are the authors' own prior estimates, so the study is not independent of them. Scope-2 water for electricity generation is not covered; WUE here is on-site only. The authors flag AI-specific cooling PUE and WUE as a major source of uncertainty in current national estimates and call for data collection on it.

## Relation to existing corpus

These WUE values sit below the on-site WUE figures used for hyperscale AI serving elsewhere in this folder. Google's LLM-serving fleet WUE of 1.15 L/kWh in `research/water/017-google-2025-gemini-water-measurements.md` is above the 0.56-0.96 L/kWh estimated for US midsize facilities here, which cuts against the assumption that non-hyperscale facilities are uniformly more water-intensive per unit of IT energy. The same file's on-site-only boundary matches the boundary used here, so the two are directly comparable.

---
Retrieved: 2026-09-19
Search: OpenAlex for DOI 10.1016/j.enbuild.2025.115734 → OSTI/eScholarship accepted manuscript PDF (ScienceDirect 403s automated requests)
