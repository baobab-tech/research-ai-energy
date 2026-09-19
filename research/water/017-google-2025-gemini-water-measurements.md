# Median Gemini Apps Text Prompt: 0.24 Wh and 0.26 mL of On-Site Cooling Water

**Topic:** Water — first-party production measurement of per-prompt water and energy; what a WUE Category 2 boundary includes
**Source:** Cooper Elsworth, Keguo Huang, David Patterson, Ian Schneider, Robert Sedivy, Savannah Goodman, Ben Townsend, Parthasarathy Ranganathan, Jeff Dean, Amin Vahdat, Ben Gomes, James Manyika (all Google), 2025
**Type:** preprint (arXiv, not peer reviewed)
**URL:** https://arxiv.org/abs/2508.15734
**Published:** 2025-08

## Finding

Google reports 0.24 Wh and 0.26 mL of water for the median Gemini Apps text prompt in May 2025, measured from internal fleet telemetry rather than modelled from hardware specifications. The water figure is not a measurement of water: it is the measured IT energy multiplied by a fleet-average WUE of 1.15 L/kWh, and WUE Category 2 counts only freshwater consumed inside the facility. Water consumed generating the electricity, water embodied in chip manufacture, and all training water fall outside the boundary. The 33x and 44x reductions are year-on-year changes in energy and in emissions between May 2024 and May 2025; the paper reports no equivalent time series for water.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Water per prompt, comprehensive | 0.26 mL | (E_total − E_overhead) × WUE; on-site cooling consumption only, WUE Category 2 (ISO/IEC 30134-9), median Gemini Apps text prompt, May 2025 |
| Water per prompt, narrow boundary | 0.12 mL | Same formula on the narrow energy figure; accelerators only, sampled from the 10% most efficient data centres |
| Energy per prompt, comprehensive | 0.24 Wh | Active accelerators 0.14 + host CPU/DRAM 0.06 + idle capacity 0.02 + facility overhead 0.02; fleet average; measured at the PSU |
| Energy per prompt, narrow | 0.10 Wh | Active accelerators only, top-10% most efficient data centres; excludes the other three components |
| Ratio, comprehensive to narrow energy | 2.4x | Same fleet, differing only in measurement boundary and utilisation sampling |
| Google WUE, LLM-serving fleet | 1.15 L/kWh | Category 2, prior calendar-year average; identical value for 2023 and 2024 |
| Share of withdrawn water consumed | ~80% | Google fleet average |
| Emissions per prompt | 0.03 gCO2e (0.023 Scope 2 market-based + 0.010 Scope 1+3) | Market-based, so it credits clean-energy purchases; embodied accelerator emissions amortised |
| Energy reduction, May 2024 to May 2025 | 33x | Software efficiency only: 23x from model improvements × 1.4x from machine utilisation |
| Emissions reduction, same period | 44x | 33x energy × 1.4x reduction in market-based grid emissions intensity; Scope 1+3 fell 36x, Scope 2 MB fell 47x |
| Google fleet PUE | 1.09 | Fleet-wide average, self-reported |
| Stated comparisons | 9 seconds of television (0.24 Wh); 5 drops of water at 0.05 mL per drop (0.26 mL) | Authors' framing |

## Methodology

Every LLM model serving the Gemini app is identified, including supporting models for scoring, ranking, classification and prompt routing. Those models are mapped to job IDs and machine IDs, and power-supply-unit energy is measured for those machines during inference. Energy is decomposed into active accelerator, active host CPU and DRAM, idle provisioned capacity, and campus PUE overhead, then divided by total Gemini Apps prompt count over the same period. The reported figure is the median prompt: models are ranked by energy per prompt and the model serving the 50th-percentile prompt is selected.

Water is derived, not metered per prompt: Water/prompt = (E_total − E_overhead) × WUE. Subtracting the overhead term recovers IT energy, which is the denominator WUE is defined against. WUE is the prior calendar year's fleet average for data centres supporting LLM models, used to normalise away seasonal and site variation.

Stated exclusions: external networking (no operational control), end-user devices, and LLM training and data storage, which the authors defer to future work.

## Limitations and conflicts

Every author is employed by Google. The data, the instrumentation, the WUE, the PUE and the emissions factors are Google's own and are not externally audited. The paper is a preprint and has not been peer reviewed.

The 0.26 mL is a product of two numbers, only one of which is measured per prompt. The WUE of 1.15 L/kWh is an annual fleet aggregate, so the figure carries no information about water consumption at any particular site or season; a prompt served in Arizona in August and one served in Finland in January produce the same reported number. Water consumed at generating plants is outside the boundary and is not discussed. Training water is excluded, and training is where the water footprint literature has concentrated. The median is a choice: the paper gives no distribution, so the water cost of a long prompt is not recoverable from it. The year-on-year comparison uses May 2024 as its baseline without stating what mix of models that baseline represents, and the gains attributed to model improvements are inseparable from changes in which models serve the median prompt.

The paper compares its 0.26 mL to "previous estimates of 45 to 50 mL" without noting that those estimates use wider boundaries.

## Relation to existing corpus

`research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md` reconstructs this figure from Google's own published inputs and obtains 0.254 mL, agreeing to within 2.3%, then adds a generation-water term of 0.471 mL at a US thermoelectric intensity of 1.80 L/kWh for a boundary-complete 0.725 mL. That paper also puts a long Gemini prompt at 9.2 Wh and 28 mL total.

The comparison against `research/water/001-li-2023-making-ai-less-thirsty.md` and `research/water/018-li-2025-cacm-ai-water-projections.md` is boundary-mismatched as usually stated. Li et al.'s comparable scope-1 figure is 2.200 mL per medium request on US-average Microsoft assumptions, against 0.26 mL here; their 16.904 mL includes generation water and is not the right comparator.

---
Retrieved: 2026-09-19
Search: arXiv PDF https://arxiv.org/pdf/2508.15734, full text via pdftotext
