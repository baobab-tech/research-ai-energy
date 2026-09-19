# US small data centres showed no PUE improvement between 2012 and 2018, holding at 1.82–2.28 while midsize facilities fell to 1.43–1.76

**Topic:** Data-centre infrastructure — the efficiency of the non-hyperscale installed base
**Source:** Lei, N.; Ganeshalingam, M.; Masanet, E.; Smith, S.; Shehabi, A. — Lawrence Berkeley National Laboratory, with UC Santa Barbara, 2025
**Type:** peer-reviewed (LBNL authors; *Energy and Buildings* 339)
**URL:** https://doi.org/10.1016/j.enbuild.2025.115734
**Source note:** Accepted manuscript retrieved from https://www.osti.gov/pages/servlets/purl/3398559 (CC BY). eScholarship permalink https://escholarship.org/uc/item/3qj3j2wv. Code and data at https://github.com/nuoaleon/Shedding-Light-on-U.S.-Small-and-Midsize-Data-Centers-Exploring-Insights-from-the-CBECS-Survey
**Published:** 2025-07

## Finding

Efficiency gains in the US data-centre stock did not reach the small end of it. Across the two CBECS survey years, estimated PUE for US small data centres was flat at 1.82–2.29 in 2012 and 1.82–2.28 in 2018, while midsize facilities improved from 1.46–1.83 to 1.43–1.76 on the back of air economizer and evaporative cooling adoption. Under 17% of small data centres used an air economizer at all; direct expansion units remained the dominant system in both size classes.

The stock itself shrank over the period, from 1.764 million to 1.398 million small and midsize facilities holding 5.177 million down to 4.262 million servers, consistent with migration to cloud. The efficiency implication runs the other way from the water one: midsize facilities bought their lower PUE with water, since water-cooled chillers raised their aggregate WUE from 0.52–0.86 to 0.56–0.96 L/kWh over the same years while small facilities, on water-light direct expansion, saw WUE fall.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Small data centre PUE | 1.82–2.29 (2012) → 1.82–2.28 (2018) | kWh/kWh; estimated from cooling-system market share weighted by county-level server counts |
| Midsize data centre PUE | 1.46–1.83 (2012) → 1.43–1.76 (2018) | Same method |
| Small data centre WUE | 0.26–0.42 (2012) → 0.21–0.35 (2018) | L per kWh of IT electricity; site water only |
| Midsize data centre WUE | 0.52–0.86 (2012) → 0.56–0.96 (2018) | Same |
| Small/midsize facility count | 1.764M (2012) → 1.398M (2018) | CBECS survey weights; −21% |
| Server count in those facilities | 5.177M (2012) → 4.262M (2018) | CBECS; −18% |
| Servers housed in office buildings | over 40% of small-DC servers; 55% of midsize-DC servers | By principal building activity |
| Geographic concentration | over half of all servers in IECC zones 5A, 3A, 4A | Zones assigned via county-level server allocation |
| Air economizer penetration, small DCs | under 17% of cooling systems | 2018 |
| Evaporative cooling, midsize DCs | 0.2% → 5.2% | 2012 to 2018 |
| Deployments with fewer than 4 servers | about a quarter of small data centres in 2018 | CBECS |
| Size class definitions | small 1–25 servers, ≤1000 ft²; midsize 26–499, 1001–20,000 ft² | Large (≥500 servers) excluded from scope |
| LBNL 2024 report comparison | small 2.23 (2010) → 2.06 (2018); midsize 1.78 → 1.64 | Independent estimate the authors cross-check against |

## Methodology

CBECS microdata for 2012 and 2018, the survey years available. Buildings housing servers were classified small, midsize or large using reported server and rack counts, computer-area square footage and gross building area against IDC data-centre environment definitions. Large facilities were excluded because CBECS codes any building with 500 or more servers into a single category (`9995`), leaving roughly 1,843 and 2,373 weighted buildings in 2012 and 2018 that cannot be resolved further; hyperscale is therefore out of scope by construction.

PUE and WUE were not measured or surveyed. They were estimated by mapping CBECS-reported cooling system types onto PUE and WUE values by cooling system, climate zone and size from the authors' own prior published estimates, then taking a weighted average with county-level server counts as weights. County server counts were themselves modelled: CBECS microdata omits geography below census division, so the authors allocated servers to counties using the linear association between server count and workforce size, with BLS Occupation Employment Statistics for 2012 and 2018 and a mapping from occupations to CBECS building activity categories.

The reported PUE and WUE bands are the 5th to 95th percentile spread of that distribution, reflecting within-cooling-system variation in equipment efficiency and operating settings.

## Limitations and conflicts

Funding: US Department of Energy, Office of Energy Efficiency and Renewable Energy, Industrial Efficiency and Decarbonization Office; Lawrence Berkeley National Laboratory under contract DE-AC02-05CH11231. No industry funding and no commercial interest is disclosed or apparent. Data and code are public.

The efficiency figures are estimates, not observations. Two modelling layers sit between the survey and the numbers: PUE and WUE come from the authors' earlier cooling-system-type estimates rather than from any metered facility in CBECS, and the spatial weights come from a workforce-to-server regression rather than from known locations. The authors flag that this regression is not expected to hold for large cloud and AI facilities.

The data end in 2018. Nothing here describes the AI buildout, and the authors say so, calling out AI-specific cooling PUE and WUE as a major uncertainty that current surveys do not collect. A CBECS survey year after 2018 would be needed to say whether small-facility PUE has moved since.

## Relation to existing corpus

Supplies the defensible non-hyperscale PUE counterweight that `015-setyo-2025-dc-energy-efficiency-thermal-review.md` does not: the small-facility band of 1.82–2.28 rests on a national survey with published code, where Setyo's 2.23 is the reciprocal of a mean of six undated power-breakdown diagrams.

Consistent with `016-lbnl-2026-us-dc-energy-2025-update.md`, which models a US national average PUE of 1.45 in 2024 against 1.55 in 2018 and 1.145 for AI-serving facilities. A fleet average in the mid-1.4s alongside a small-facility band above 1.8 implies the national figure is carried by large low-PUE sites, which is what both reports say.

Begins where `004-kim-2024-data-center-pue-economizers.md` ends: that study models 1.16–1.43 for an optimised new-build air-cooled hall, this one estimates 1.43–1.76 and 1.82–2.28 for the installed midsize and small stock.

The water side of the same source, including the PUE-WUE trade-off in detail, is covered in `../water/022-lei-2025-us-midsize-data-centers-wue.md`.

---
Retrieved: 2026-09-19
Search: DOI 10.1016/j.enbuild.2025.115734 (Elsevier 403); accepted manuscript via OSTI purl 3398559
