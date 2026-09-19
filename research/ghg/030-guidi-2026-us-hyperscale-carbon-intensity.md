# 403 US hyperscale data centres drew 68-99 TWh and emitted 37-54 MtCO2 in one year, at a carbon intensity 48% above the US grid average

**Topic:** GHG emissions — facility-level US hyperscale emissions and the siting/carbon-intensity penalty
**Source:** Guidi, Dominici, Squartini, Sprinkle, Gilmour, Butler, Bell, Delaney, Bargagli-Stoffi — Harvard T.H. Chan School of Public Health, University of Pisa, IMT Lucca, Esri, Baxtel, UCLA, 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2606.05420
**Published:** 2026-06-03

## Finding

Facility-level attribution rather than top-down modelling. The authors identified 403 US hyperscale data centres operating May 2024-April 2025, matched each to the generating plants in its balancing authority using EPA eGRID plant-level data, and derived 68-99 TWh of consumption (central scenario ~82 TWh) and 37-54 MtCO2 (central ~45 Mt). The substantive result is not the total but the intensity: the electricity-weighted average carbon intensity attributable to these facilities is ~545 gCO2/kWh, about 48% above the contemporaneous US national average of ~370 gCO2/kWh, with roughly 54% of attributed generation from fossil fuels. Hyperscale siting is systematically dirtier than the national grid, not cleaner.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Facilities | 403 | Contiguous US, May 2024-Apr 2025, satellite-validated |
| Electricity, central scenario | ~82 TWh (u = 0.58) | Facility-load scenarios u ∈ {0.48, 0.58, 0.663, 0.70} give 68 / 82 / 93 / 99 TWh |
| Share of US electricity, central | ~1.8% | |
| CO2, central | ~45 Mt (range 37-54 Mt) | Attributional, eGRID2023 |
| HDC electricity-weighted carbon intensity | ~545 gCO2/kWh | vs US national average ~370 gCO2/kWh (2023) |
| Excess over national average | +48% | |
| Fossil share of attributed generation | ~54% | |
| Virginia | ~21 TWh (~25% of sample) | Highest state |
| Oregon / Ohio / Iowa | ~11 / ~9 / ~7 TWh | Top four states >50% of total |
| Sample coverage vs IEA benchmark | IEA implies ~120 TWh US hyperscale in 2024 | So this sample is a large but partial subset |
| Ratio to prior published estimate | ~3.6x the 22.85 TWh of Siddik et al. | |

## Methodology

Attributional, not consequential. Facility-level nameplate and load data were compiled from heterogeneous commercial sources (Baxtel) and validated against satellite imagery, then combined with a bottom-up power-flow model and an independent PUE-implied consistency check to set the central utilisation factor u = 0.58. Emissions come from EPA eGRID2023 plant-level data for the balancing authorities containing each facility. The 68-99 TWh spread is a utilisation-scenario range, not a statistical confidence interval — the dominant uncertainty is how hard the facilities are actually run, which is unobservable.

## Limitations and conflicts

Academic authorship with two commercial co-author affiliations: Esri (geospatial software) and Baxtel (the data-centre market intelligence firm that is also a data source), which should be recorded as a supplier relationship even though neither sells the result. Preprint, not yet peer reviewed as of retrieval. Attributional accounting assigns each facility the average emissions of its balancing authority's generation mix, which credits nothing for power purchase agreements and penalises nothing for marginal dispatch — a different question from what a consequential analysis would answer, and the 545 gCO2/kWh figure should not be read as the marginal emissions of adding load. Covers hyperscale only, so it excludes the ~40% of US servers in small and midsize facilities. Uses eGRID2023 against a May 2024-April 2025 study period, a one-to-two year lag during which grids changed.

## Relation to existing corpus

No direct overlap; first facility-level US emissions attribution in the corpus. Sits inside the LBNL denominator (025): ~82 TWh hyperscale against 176 TWh all US data centres in 2023. The 545 vs 370 gCO2/kWh gap is the empirical counterweight to the market-based accounting in 028 and 029, which reports those same grids as near-zero. Complements `research/datacenters/012-lei-2025-us-small-midsize-dc-cbecs.md` on the non-hyperscale remainder.

---
Retrieved: 2026-09-19
Search: WebSearch "Assessing the Carbon Emissions and Energy Consumption of U.S. Hyperscale Data Centers"; arXiv PDF 2606.05420 extracted locally
