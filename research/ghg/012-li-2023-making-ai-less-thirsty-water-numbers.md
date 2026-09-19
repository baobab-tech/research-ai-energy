# Carbon-optimal and water-optimal training schedules conflict: siting LaMDA where solar is abundant minimises CO2e and maximises evaporation

**Topic:** GHG emissions — carbon-aware scheduling of AI training, and its side effects
**Source:** Pengfei Li, Jianyi Yang (UC Riverside), Mohammad A. Islam (UT Arlington), Shaolei Ren (UC Riverside), 2023
**Type:** preprint (arXiv; v1 2023-04-06, current v5 2025-03-26)
**URL:** https://arxiv.org/abs/2304.03271
**Published:** 2023-04 (v5 revision 2025-03)

## Finding

Carbon-aware scheduling, the practice of moving AI training to the hours and locations where the grid is cleanest, works against water efficiency. Running the same LaMDA training job across four Google US sites and twelve possible start months in 2022, the authors find the carbon-minimising choice is not the water-minimising one: Nevada gives a low carbon footprint because of high solar penetration and a high water footprint because of high temperatures driving cooling-tower evaporation. The later revision generalises this to a diurnal rule, "follow the sun" for carbon and "unfollow the sun" for water. Separately, recomputing LaMDA's training emissions on a location-based basis with time-varying state fuel mixes places them between 80 and 200 tCO2e, against the roughly 25 tCO2e implied by the fixed 0.056 kgCO2e/kWh factor Google reported for the same run.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| LaMDA training energy | 451 MWh | taken from Thoppilan et al.; secondary citation |
| Carbon factor Google applied to LaMDA | 0.056 kgCO2e/kWh | fixed factor, no fuel-mix detail disclosed; market-based |
| LaMDA training emissions implied by that factor | ~25 tCO2e | 451 MWh × 0.056; derived |
| LaMDA training emissions, this paper | 80-200 tCO2e | range spanned by the Figure 4(c) axis across 4 sites × 12 start months; modelled, location-based, no carbon credits (footnote 4) |
| Implied location-versus-market gap | ~3-8x | derived from the two rows above |
| Sites modelled | Loudoun County VA, Henderson NV, Midlothian TX, The Dalles OR | Google US data centres |
| Training duration modelled | 57.7 consecutive days | from the LaMDA paper |
| PUE assumed | 1.1 | representative of Google's best, not measured for this run |
| Spread in water footprint across the same choices | highest >3x the lowest | modelled |
| Direction of the conflict | Nevada: low carbon (solar), high water (heat) | worked example |
| Water-generation factors used | coal 1.7, nuclear 2.3, gas 1.1, solar 0, wind 0, other 1.8 L/kWh | median EWIF by fuel type, hydropower excluded |

## Methodology

An hour-by-hour simulation of a 57.7-day training run, repeated for each of four Google US sites and each possible start month in 2022. Inputs are 2022 hourly weather data (dry-bulb temperature and relative humidity, converted to wet-bulb), state-level hourly electricity fuel mix, an empirical cooling-tower model at five cycles of concentration, and a fixed PUE of 1.1. Carbon intensity is derived from the same state-level fuel mix as a weighted average, which footnote 4 states deliberately reflects physical generation rather than purchased credits. Nothing is measured: Google disclosed neither the sites, the start date, nor the runtime PUE, and the authors say their estimate serves as an approximate reference point rather than a calculation of the actual footprint. The carbon figures appear only as a plotted curve; no table of carbon values is given.

## Limitations and conflicts

Academic authors at UC Riverside and UT Arlington; no industry funding or affiliation disclosed and none apparent. The carbon estimate is the weakest part of the paper, which is a water paper: it exists as a foil for the water result, is never stated numerically in the text, and can only be bounded from the figure axis, so the 80-200 tCO2e range is the plotted range rather than a reported value. The underlying energy figure is secondary. The 3-8x gap against Google's reported number conflates two differences at once, location-based versus market-based accounting and modelled versus disclosed fuel mix, and the paper does not separate them. Whether the conflict generalises beyond these four sites and this year is untested.

## Relation to existing corpus

The location-versus-market gap found here anticipates what later first-party disclosures quantify directly: `research/ghg/027-schneider-2025-tpu-lifecycle-embodied-emissions.md` reports Google's TPU operational emissions as 2.7x higher location-based than market-based, and `research/ghg/028-google-2026-environmental-report-accounting-gap.md` and `research/ghg/029-microsoft-2026-sustainability-report-fy25.md` document the same gap at corporate scale. The market-based factor criticised here is the same class of figure that supplies 6.4x of the efficiency ratio in `research/ghg/015-tpu-v4-energy-efficiency-numbers.md`. `research/water/001-li-2023-making-ai-less-thirsty.md` covers the water side of this paper.

---
Retrieved: 2026-09-19
Search: arXiv 2304.03271; v1 and v5 PDFs extracted locally
