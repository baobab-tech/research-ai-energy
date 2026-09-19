# 68% of Google's 41 Mt "AI solutions" climate benefit is attributed to Google Earth, on an unverified counterfactual

**Topic:** narrative — corporate avoided-emissions claims, attribution and counterfactual
**Source:** Google, 2026 — *Google 2026 Environmental Report*
**Type:** corporate disclosure
**URL:** https://sustainability.google/files/google-2026-environmental-report.pdf
**Published:** 2026-06

## Finding

Google claims nine of its products helped others reduce 41 million tCO2e in 2025, presented under the heading "AI solutions" and framed as "roughly three times Google's own emissions." 27.8 Mt of that — 68% — is attributed to Google Earth, on the basis that developers interviewed by Google used Earth imagery somewhere between siting and construction of solar and onshore wind plants; Google then counts the full annual emissions displacement of every such plant built by those developers since 2020. No attribution fraction is applied and no additionality test is described. Google states for each product line: "The data and claims have not been independently verified." Google's own total ambition-based emissions in 2025 were approximately 14.5 Mt CO2e, of which scope 3 was 11.6 Mt, and its supply-chain emissions grew 25% year on year on AI infrastructure.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Total "enabled emissions reductions", 2025 | 41 million tCO2e | Nine products; counterfactual estimate; not in GHG inventory |
| Google Earth | 27.8 Mt tCO2e | Full generation of solar/wind plants built by interviewed developers, 2020–2025 vintage, counted in 2025 |
| Nest thermostats | 8.8 Mt tCO2e | Savings % from US/UK studies generalised worldwide; EPA AVERT marginal factors for US 95% |
| Fuel-efficient routing in Google Maps | 3 Mt tCO2e | — |
| Solar API | 1.3 Mt tCO2e | Buildings with a solar permit within 6 months of an API call |
| Ignite Energy Access | 280 kt tCO2e | UNFCCC solar-lamp methodology, 0.092 tCO2e/lamp/yr |
| Alternative route suggestions / Waymo / Green Light / Contrails | 75 kt / 18 kt / 13 kt / 3 kt tCO2e | Waymo and Green Light are ~0.04% and ~0.03% of the total |
| Google total ambition-based emissions, 2025 | ~14.5 Mt CO2e (scope 3: 11.6 Mt) | Market-based |
| Separate claim: emissions "avoided" in own operations and supply chain | >58 Mt tCO2e | Different counterfactual; explicitly not additive to the 41 Mt |
| Contrails model | 380 tCO2e compute vs 3 000 tCO2e avoided | The only claim in the report where AI compute cost is netted against benefit |

## Methodology

Attributional counterfactual. Google's stated definition: "We estimate avoided emissions by comparing our actual emissions to a scenario where we didn't take action." For the enabled-product figures the chain is: identify users of the product, assume the product was causally significant, model the physical effect with third-party tools (NREL PVWatts and Cambium, EIA capacity factors, LBNL *Tracking the Sun* and the Land-Based Wind Market Report, EPA AVERT), and count the full effect.

Three features drive the size of the number:
1. **No attribution weighting.** For Google Earth, Google "interviewed partners that use Google Earth to understand the significance it played in their process (from siting to construction) and considered all the solar and onshore wind power plants built by the developers." The word "all" does the work; no fractional attribution is disclosed.
2. **Stock counted as flow.** Projects enabled "prior to 2025 (dating back to 2020)" contribute to the 2025 annual figure. The number is a cumulative installed base reported as an annual benefit, so it grows mechanically each year.
3. **Correlation as causation for Solar API.** Installations are counted when a building "had a publicly issued solar permit within six months of the API call."

Google Earth is satellite and aerial imagery, not a machine-learning system, yet supplies two-thirds of a figure headlined "AI solutions."

## Limitations and conflicts

Self-reported by the party making the claim, with no assurance. Google's own footnotes concede the weaknesses: "Enabled emissions reductions estimates include inherent uncertainty due to factors that include the lack of primary data and precise information about real-world actions and their effects to date"; "Google is relying on its own substantiation of the enabled emissions-reduction impact"; "The data and claims have not been independently verified." Nest savings percentages measured in the US and UK are "generalized for Nest thermostat usage worldwide, assuming user opt-in for available energy-saving features."

Nothing is netted. The 41 Mt is not offset against Google's own 14.5 Mt, and Google's framing runs the other way — the claim's purpose is the ratio ("roughly three times Google's own emissions"). The same 27.8 Mt of renewable generation is also, in all probability, claimed by the developers who built the plants, by the utilities procuring them, and by corporate offtakers, which is the double-counting problem the accounting literature identifies (see 023).

For contrast, Microsoft's *2026 Environmental Sustainability Report* (published July 2026, https://www.microsoft.com/en-us/corporate-responsibility/topics/sustainability/report/) publishes **no** quantified emissions-reduction claim for its AI-for-sustainability work — its "Applying AI for sustainability" section reports water volumes, detection accuracies and project counts only. Microsoft's own FY25 emissions were 20 290 000 tCO2e, up 25% from 16 215 000 in FY24, with scope 2 rising from ~2% to 13% of the total. Two firms with comparable AI-for-climate portfolios therefore differ by 41 Mt in what they are willing to claim.

## Relation to existing corpus

No direct overlap. Supplies the corporate primary source for the enablement claim, and is the concrete instance of the methodological fragmentation documented in `narrative/023-okeeffe-brander-2026-avoided-emissions-methodology-comparison.md`.

---
Retrieved: 2026-09-19
Search: WebSearch "Google 2026 environmental report AI avoided emissions methodology"; full PDF downloaded and text-extracted
