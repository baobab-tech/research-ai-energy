# A literature review derives a PUE of 2.23 as the reciprocal of a 44.8% mean IT-power share taken from six mixed-provenance power breakdowns

**Topic:** Data-centre infrastructure — efficiency metrics, what published PUE averages represent
**Source:** Setyo, Z.G.M.; Rijal, H.B.; Aqilah, N.; Abdullah, N. (Tokyo City University; Universiti Teknologi Malaysia), 2025
**Type:** peer-reviewed (literature review)
**URL:** https://doi.org/10.3390/en18143689
**Source note:** Open-access PDF retrieved from https://mdpi-res.com/d_attachment/energies/energies-18-03689/article_deploy/energies-18-03689.pdf
**Published:** 2025-07

## Finding

The 2.23 figure attributed to this review is not a measured fleet average. It is the reciprocal of a single number: the unweighted arithmetic mean of the IT-equipment share of total power reported in six power-breakdown sources the authors tabulated (52%, 50%, 36%, 29%, 50%, 52%), giving 44.8%, and PUE = 1 / 0.448 = 2.23. Four of those six are illustrative "typical data centre" pie charts published in other papers, one is a simulation output, and one is a measured reading from a single facility in Linköping, Sweden. No facility is dated, sized or identified by type, and the authors state that none of the reviewed studies specified whether the data centre was hyperscale, colocation or enterprise.

The review's substantive contribution is the gap it documents, not the number: published data-centre power reporting does not consistently distinguish IT from facility power, so terms such as "power supply system", "power conversion" and "other equipment" cannot be allocated to either side of the PUE ratio without the reviewer's judgement.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Corpus reviewed | 39 papers + 9 websites | Authors' count; ~80% of studies from Asian regions |
| Sources in the power-breakdown table | 6 | 4 illustrative "typical" breakdowns, 1 simulation, 1 measured single facility |
| Mean IT-equipment power share | 44.8% of total facility power | Unweighted mean of 6 percentages; mixed measured/simulated/illustrative |
| Derived PUE | 2.23 | Calculated as 1 / 0.448; not a measured or fleet-weighted PUE |
| Individual IT shares behind the mean | 52, 50, 36, 29, 50, 52 (%) | Implied individual PUEs 1.92, 2.00, 2.78, 3.45, 2.00, 1.92 |
| Facility-power mean as printed | 51.2% (table) / 51.4% (prose) | Inconsistent with the same table's own column, which averages 55.2% |
| Indoor air temperature "average" | 16.5 °C, 19% RH | Single facility (Medan, Indonesia); the 5-row table's own means are 22.5 °C and 38.8% RH |
| Indoor temperature range across 5 facilities | 15–34 °C | Measured; 5 facilities in Indonesia, Hong Kong and Oakland, USA |
| Indoor relative humidity range | 17–68% | Measured; same 5 facilities |
| ASHRAE allowable envelope | 15–32 °C, 20–80% RH | Recommended: 18–27 °C, 60% RH |
| Passive cooling applicability | Hyperscale and colocation, not small/medium business | Authors' qualitative judgement, marked in the source as their own interpretation |

## Methodology

Narrative review. For the power analysis the authors took equipment-level power breakdowns from six prior publications and reassigned each line item to IT or facility power using their own classification rules, then averaged the resulting IT shares across sources with equal weight and inverted the mean. No facility floor area, IT load, measurement period, instrument or year is attached to any of the six sources. The thermal analysis tabulates measured indoor and outdoor temperature and humidity from five facilities and compares them against ASHRAE Thermal Guidelines. The thermal-comfort section uses data from computer labs because the authors found no thermal-comfort study conducted in a data centre.

## Limitations and conflicts

Funding: Tokyo City University covered the article processing charge. The authors declare no conflict of interest; no industry funding is disclosed and none is apparent.

The 2.23 figure does not support use as a counterweight to hyperscaler PUE claims of 1.1 to 1.4, and should not be cited that way. Three defects stand in the way. First, population: six undated, unidentified breakdowns, four of them illustrative diagrams rather than facility data, is not a fleet. Second, period: none of the six is dated in the review, and the underlying sources include work from 2007 onward, so the figure carries no reference year. Third, method: inverting a mean of shares is not the mean of the corresponding PUEs (that would be 2.35), and neither is a capacity-weighted or energy-weighted average, which is what a fleet PUE requires.

The review's own arithmetic does not close. The facility-power column of the same table averages 55.2%, not the 51.2% printed in the table or the 51.4% in the surrounding text, and 44.8 + 51.2 does not sum to 100. The abstract's claim that indoor air temperatures "averaged 16.5 °C with 19% relative humidity" reproduces a single row of the thermal table rather than any average of it, and at 19% RH that row sits below ASHRAE's allowable lower bound of 20%, contradicting the abstract's statement that the temperatures remain within the allowable range. The authors disclose the geographic skew themselves: roughly 80% of reviewed studies are from Asian regions.

## Relation to existing corpus

Contradicted as an efficiency benchmark by two better-bounded estimates in this corpus. `016-lbnl-2026-us-dc-energy-2025-update.md` models a US national average PUE of 1.45 in 2024 and 1.145 for AI-serving facilities. `012-lei-2025-us-small-midsize-dc-cbecs.md` estimates 1.82–2.28 for US small data centres and 1.43–1.76 for midsize in 2018 from survey-weighted cooling-system distributions. The Lei figures are where a defensible non-hyperscale counterweight comes from: the small-data-centre band genuinely brackets 2.2, and it rests on a national survey rather than on six pie charts.

Reference [7] of this review is `004-kim-2024-data-center-pue-economizers.md`, which supplies its modelled climate-zone PUE material.

Independent of the number, the review's documented defect (published breakdowns do not consistently separate IT from facility power) is the same structural objection to PUE made from the opposite direction in `023-verrus-2026-pue-critique-pux.md`, where waste inside the IT envelope leaves the ratio unchanged or improves it.

---
Retrieved: 2026-09-19
Search: DOI 10.3390/en18143689; open-access PDF via mdpi-res.com
