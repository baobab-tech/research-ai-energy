# Google's headline "58 million tCO2e avoided" is arithmetically the gap between its two Scope 2 accounting methods

**Topic:** Greenwashing evidence — market-based vs location-based Scope 2; avoided-emissions claims
**Source:** Google/Alphabet, 2026 Environmental Report (calendar year 2025)
**Type:** corporate disclosure
**URL:** https://sustainability.google/files/google-2026-environmental-report.pdf
**Published:** 2026-06-30

## Finding

Google reported 2025 Scope 2 emissions of 2,815,000 tCO2e market-based and 15,148,700 tCO2e location-based — a 12.33 Mt gap, with the location-based figure 5.4x the market-based one. Google's front-page claim of "over 58 million tCO2e avoided" is defined in the report's own endnotes as the difference between market-based and location-based accounting (for operations) plus an equivalent counterfactual for the supply chain. Endnote 142 states of the 2012-2025 operational portion: "This estimate hasn't been independently verified." Google's headline "operational emissions" figure (Scope 1 + Scope 2 market-based, 2,901,100 tCO2e) fell 2.3% in 2025 while its location-based Scope 2 rose 36.9% and its electricity consumption rose 37%.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Scope 2 location-based 2025 | 15,148,700 tCO2e | grid-average hourly emission factors |
| Scope 2 market-based 2025 | 2,815,000 tCO2e | GHGP market-based, incl. PPAs and Granular Certificates |
| Gap 2025 | 12,333,700 tCO2e (5.4x) | difference of the two methods |
| Scope 2 location-based 2024 → 2025 | 11,067,100 → 15,148,700 (+36.9%) | grid-average factors |
| Scope 2 market-based 2024 → 2025 | 2,898,600 → 2,815,000 (−2.9%) | GHGP market-based |
| Scope 2 location-based 2019 → 2025 | 5,173,000 → 15,148,700 (+193%) | grid-average factors |
| Operational emissions (S1 + S2 market-based) 2025 | 2,901,100 tCO2e (−2.3% YoY) | Google's headline metric |
| Operational emissions vs 2019 | +240% | Google's own statement |
| Claimed avoided emissions 2025 | >58,000,000 tCO2e | location-based minus market-based, plus supply-chain counterfactual |
| Compute carbon intensity, market-based | reported basis | gCO2e/EFLOP |
| Same CCI under location-based accounting | 793, 712, 195 gCO2e/EFLOP | Google's own restatement, endnote 48 |

## Methodology

Google reports Scope 2 under both GHGP methods. Location-based uses hourly grid emission factors; market-based applies environmental attribute certificates from PPAs, other clean energy agreements and Granular Certificates. Endnotes 142, 144 and 147 define avoided emissions as a comparison of market-based Scope 2 against location-based Scope 2 — "the emissions we would have reported if we didn't use any market-based interventions." The supply-chain portion compares value-chain emissions against "a location-based baseline scenario where no clean electricity was procured by Google or our suppliers."

Google's 2025 Scope 2 market-based and location-based figures were subject to third-party limited assurance; the 2012-2025 cumulative avoided-emissions estimate was not (endnote 142). Google also discloses that reporting its AI accelerator carbon intensity on a location-based basis would raise the operational component to 793, 712 and 195 gCO2e/EFLOP for the three TPU generations shown, and would cut the embodied share of its Ironwood chip's total intensity from 23% to 8%.

## Limitations and conflicts

Self-reported. The avoided-emissions construct is not an emissions measurement: it is the arithmetic difference between two accounting conventions applied to the same physical electricity, so it rises automatically as the grid the company draws from gets dirtier or as consumption grows. Google does not claim otherwise in the endnotes, but the figure appears without that qualification in the report's highlights. Google's position is that its contracted clean energy (12 GW added) does displace grid generation; the consequential question of how much emission that displacement actually causes is not addressed by either GHGP method. Google publicly supported the GHG Protocol's proposed stricter Scope 2 rules, unlike several peers.

## Relation to existing corpus

No direct overlap. Complements `research/washing/017-microsoft-2026-unbundled-rec-withdrawal.md`: Microsoft removed the certificate layer and its market-based number jumped; Google retained it and its market-based number fell while grid emissions rose 37%. Both document the same mechanism from opposite directions.

---
Retrieved: 2026-09-19
Search: Web search "Google 2026 Environmental Report location-based market-based Scope 2"; PDF text extracted from the full report
