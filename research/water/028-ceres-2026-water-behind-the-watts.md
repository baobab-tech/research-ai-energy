# Water Withdrawn to Generate Data-Centre Electricity in Seven US States: 3.4 Trillion Gallons in 2024, Projected 4.1-7.6 Trillion by 2030

**Topic:** Water — off-site (scope-2-equivalent) water embedded in purchased electricity; siting relative to water stress
**Source:** Ceres, 2026
**Type:** NGO/investor-network report
**URL:** https://www.ceres.org/resources/reports/water-behind-the-watts-the-hidden-risk-of-powering-data-centers
**PDF:** https://www.ceres.org/download/6489292d-d4a5-476c-874f-72e0c8c49c22
**Published:** 2026-08

## Finding

Ceres attributes roughly 3.4 trillion gallons of 2024 freshwater **withdrawals** to the electricity purchased by data centres in seven states holding ~50% of US data centres. The report's framing claim is that generation water, not cooling water, is the larger share of a data centre's water dependency, and that by 2030 water used in electricity generation is projected to account for 72% of total US data-centre water consumption even as on-site cooling gets more efficient. The figure is a withdrawal figure, not consumption, and about 78% of the withdrawal volume across the study area is hydropower pass-through — water that runs through turbines and returns to the source. Read as a consumption number it would be badly wrong; Ceres states the choice deliberately, as a measure of risk exposure rather than depletion.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Water embedded in data-centre electricity, 7 states, 2024 | ~3.4 trillion gallons | **Withdrawal**, incl. hydropower; EPRI state data-centre electricity shares applied to plant-level withdrawals |
| Comparison | ~12x combined annual water use of Los Angeles, Phoenix and Washington DC | |
| Range across states | 25 billion gal (Ohio) to 1.4 trillion gal (California) | Data-centre-attributed withdrawal |
| 2030 projection | 4.1-7.6 trillion gallons | EPRI 2024 current/future data-centre growth scenarios |
| Generation share of total DC water by 2030 | 72% | Projected; on-site cooling the remaining 28% |
| US data-centre electricity, 2023 | ~176 TWh | Carrying ~211 billion gallons indirect water dependency at regional grid mix |
| Total freshwater withdrawal, all study-area plants | ~65 trillion gallons | ~227x LA + Phoenix + DC combined, 2024 |
| Hydropower share of study-area withdrawals | ~78% | Pass-through, not consumption |
| Electricity from water-using plants | 78% (1,142 of 1,467 TWh) | 1,434 of 3,907 active ≥1 MW plants use freshwater |
| Generation in medium-high to extremely high water stress | 66% | WRI Aqueduct 4.0 baseline annual water stress, plant locations |
| Generation in areas with ≥3 months drought | 44% | US Drought Monitor 2024 |
| Both stress and drought | 32% of study-area generation | Arizona worst: 75% of generation exposed to both |
| Illinois nuclear in high water stress | 75% of state nuclear generation | Clustered NW Illinois, Mississippi-Missouri basin |
| New/planned US DCs 2022-2025 in water-stressed areas | ~two-thirds | CA, AZ, TX, IL, VA |
| DC clustering | 9 of 10 DCs have another within 5 miles | |
| Grid mix serving US data centres | gas 40%, renewables 24%, nuclear 20%, coal 15% | |
| Projects disrupted by local water/grid opposition | $130 billion, Q1 2026 alone | |
| Phoenix region (Ceres 2025 *Drained by Data*) | DC-electricity-related water use +400%; basin water stress up to +32% | As planned DCs come online |

## Methodology

Five steps: (1) identify ≥1 MW plants with 2024 generation in VA, TX, CA, IL, GA, OH, AZ using EIA Forms 860 and 923 — 3,907 plants, of which 1,434 use freshwater (saltwater/brackish excluded); (2) aggregate reported withdrawal volumes, modelling where plants do not report, using WRI's *Guidance for Calculating Water Use Embedded in Purchased Electricity* (2020); (3) overlay plant locations with WRI Aqueduct 4.0 baseline water stress and US Drought Monitor, assuming withdrawal occurs near the plant; (4) apportion to data centres using EPRI 2024 state-level data-centre electricity shares, assuming data centres source power from their own state; (5) review corporate and utility disclosures.

Explicitly out of scope: consumption (as opposed to withdrawal), water source, seasonal variation, behind-the-meter generation, and value-chain water. Ceres calls the results "directional estimates, reflecting the scale and direction of water risk, rather than an exact accounting."

## Limitations and conflicts

Ceres is an investor-advocacy non-profit; the report is written to move corporate and utility disclosure practice, and the framing ("hidden risk") is advocacy framing. Three methodological caveats matter more than the framing:

1. **Withdrawal ≠ consumption.** The 3.4 trillion gallon headline is withdrawal. With hydropower at ~78% of study-area withdrawals and once-through thermal cooling returning most of what it takes, the consumptive figure is smaller by a large and unstated factor. The 12x-LA-Phoenix-DC comparison sets a withdrawal number against municipal *use* figures, which is not like-for-like.
2. **State-boundary attribution.** Assuming data centres draw from their own state's generation mix ignores interstate transmission and contracted generation.
3. **EPRI shares and modelled plant water** are two further estimation layers stacked on the EIA reported data.

The report gives no separate quantification of on-site cooling water for the same study area, so the "bulk of the water use" claim is asserted for 2030 (72%) rather than demonstrated for 2024 on a common consumption basis.

## Relation to existing corpus

No direct overlap — the corpus has no source on off-site/scope-2-equivalent water at all. Complements `research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md`, which makes the same boundary argument at per-query scale on a consumption basis. Supplies the siting evidence the index lists as absent. Names the only two operators found disclosing embedded generation water: Meta (discloses embedded water consumption in purchased electricity, including contracted renewables, and reports avoided consumption) and CyrusOne (reports WUE Site plus WUE Source; WUE Source down 67% since 2018, driven by renewable procurement).

---
Retrieved: 2026-09-19
Search: direct fetch of Ceres report named in task brief; PDF text extracted with pdftotext
