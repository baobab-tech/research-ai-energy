# Google's reported 2025 footprint is 14.5 MtCO2e, but its location-based Scope 2 alone is 15.1 Mt — the accounting choice hides 12.3 Mt

**Topic:** GHG emissions — corporate primary disclosure; market-based vs location-based Scope 2
**Source:** Google LLC, *2026 Environmental Report* (FY2025 data), 2026
**Type:** corporate disclosure
**URL:** https://sustainability.google/files/google-2026-environmental-report
**Published:** 2026-06-30

## Finding

Google reports total 2025 "ambition-based" emissions of 14.5 MtCO2e, up 18% on 2024, and states that operational emissions (Scope 1 + 2 market-based) *fell* 2% while electricity consumption rose 37%. Both statements are true and both depend entirely on market-based Scope 2 accounting. Google's own data table gives 2025 Scope 2 location-based emissions of 15,148,700 tCO2e against market-based 2,815,000 tCO2e — a difference of 12.3 Mt, larger than Google's entire reported footprint. On a location-based basis Scope 2 rose 37% year on year (11.07 Mt to 15.15 Mt), tracking electricity growth almost exactly, which is what one would expect when consumption grows faster than the grids supplying it decarbonise.

## Key Data

| Metric | 2024 | 2025 | Change | Basis |
|--------|------|------|--------|-------|
| Total electricity consumption | 31,713,900 MWh | 43,586,600 MWh | +37.4% | Purchased + self-generated |
| Scope 1 | 71,700 t | 86,100 t | +20% | |
| Scope 2 market-based | 2,898,600 t | 2,815,000 t | -2.9% | Renewable matching applied |
| Scope 2 location-based | 11,067,100 t | 15,148,700 t | +36.9% | Grid average intensity |
| Gap between the two | 8.17 Mt | 12.33 Mt | +51% | |
| Total ambition-based emissions | ~12.3 Mt | 14,473,100 t | +18% | GHGP-derived with Scope 3 boundary exclusions |
| Scope 3 (ambition-based) | — | 11,600,000 t (80% of total) | +25% | |
| — Capital goods + use of sold products | — | 7,634,000 t (53% of total) | | Data-centre construction, chip manufacturing |
| Global average CFE | — | ~65% | | Hourly, load-weighted |
| Regional Scope 2 LB, Asia Pacific | — | 2,246,900 t (MB 1,882,600 t) | | Least gap — carbon-heavy grids, least renewable matching |
| Water replenished | — | 7.7 bn gallons (~78% of freshwater consumption) | | |

## Methodology

Self-reported, GHG Protocol-aligned, with 2025 metrics subject to third-party *limited* assurance (the weakest assurance tier). The headline "ambition-based" metric is Google's own construct: it applies "adjustments to scope 3 — specifically ambition-based boundary exclusions and market instrument reductions beyond what GHGP currently recognizes." That is, it deducts things the GHG Protocol does not allow to be deducted. Scope 2 market-based reflects renewable energy purchases matched annually; Google separately reports a 65% hourly CFE figure that does not feed the headline emissions number.

## Limitations and conflicts

Self-reported by the emitter, with limited assurance only, using a bespoke headline metric that is not GHGP-compliant by Google's own description. Google states 2025 emissions would have been "five times larger" without its interventions — an unverified counterfactual it also notes "hasn't been independently verified." No AI-specific emissions are disclosed anywhere in the report; AI and non-AI workloads are not separated, which is the same opacity de Vries-Gao (022) identifies as the binding constraint on all external estimation. The report leads with 41 MtCO2e of "enabled" reductions and 58 Mt "avoided" — figures roughly 4x the company's reported footprint, computed with counterfactual methodologies and reported alongside inventory emissions in a way that invites netting.

## Relation to existing corpus

First corporate primary GHG disclosure in `research/ghg/`. The accounting mechanism that produces the gap is quantified across 206 companies in `research/washing/025-bjorn-2025-stricter-scope2-rules.md`. Supplies the Google-side counterpart to the water claims examined in `research/water/017-google-2025-gemini-water-measurements.md`. Parallel to 029 (Microsoft FY2025), where the same market-vs-location gap appears at similar scale. The same disclosure is examined from the greenwashing angle at `research/washing/018-google-2026-market-vs-location-based-gap.md` and `research/washing/019-google-2026-ambition-boundary-exclusions.md`; this file is the emissions-inventory reading of it.

---
Retrieved: 2026-09-19
Search: WebSearch "Google 2026 Environmental Report Scope 3 FY2025"; report PDF extracted locally
