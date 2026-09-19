# AI data centres emitted 32.6-79.7 MtCO2 in 2025 — the origin of the "80 million tonnes" figure

**Topic:** GHG emissions — aggregate AI footprint; provenance of the repo README's headline number
**Source:** Alex de Vries-Gao (Institute for Environmental Studies, VU Amsterdam; Digiconomist; De Nederlandsche Bank), 2025
**Type:** peer-reviewed (Patterns, Cell Press)
**URL:** https://pmc.ncbi.nlm.nih.gov/articles/PMC12827721/
**Source note:** DOI: 10.1016/j.patter.2025.101430
**Published:** 2025-12-17

## Finding

This is the source of the widely repeated claim that AI's 2025 greenhouse gas footprint is around 80 million tonnes CO2, "comparable to New York City." The paper estimates AI-specific data-centre emissions at 32.6-79.7 MtCO2 for 2025 — a range, not a point estimate. The "80 million tonnes" number circulating in media and in this repository's README is the **upper bound** of that range, quoted without the lower bound, which is 2.4x smaller. The NYC comparison in the paper is anchored to NYC's 52.2 MtCO2 in 2023, which sits inside the range rather than at the top of it.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| AI data-centre CO2, 2025 | 32.6-79.7 Mt | Operational (scope 1+2) only; excludes embodied/manufacturing |
| AI power demand, end-2024 | 9.4 GW | Derived from chip shipment and company disclosure analysis |
| AI power demand, end-2025 | 23 GW | Same; upper end of range |
| Carbon intensity applied | 395.65 gCO2/kWh | IEA 2024 global data-centre average |
| US-Europe weighted alternative | ~355.53 gCO2/kWh | From Apple, Google, Meta, Microsoft, Oracle, Tesla disclosures |
| AI water footprint, 2025 | 312.5-764.6 billion L | 3.4 L/kWh indirect + 0.59 L/kWh direct |
| Regional grid intensity spread | 0.17-0.46 tCO2/MWh | US regions — a 2.7x spread the central estimate averages away |
| Regional water intensity spread | 0.68-11.98 L/kWh | 18x spread |

## Methodology

Top-down. AI-attributable power demand is inferred from AI hardware production and deployment, then multiplied by an average carbon intensity taken from the IEA. Because no operator reports AI workloads separately, the author states plainly that AI impact can only be approximated "through data centers' general performance metrics." Emissions are operational only; the paper notes manufacturing is roughly 23% of ICT lifecycle impacts and is excluded. The estimate is a model output built on other models' outputs, not a measurement.

## Limitations and conflicts

De Vries-Gao runs Digiconomist, an advocacy-adjacent site that has published high-profile energy estimates for Bitcoin and AI and has been criticised for methodological opacity in the crypto case. He declares no competing interests and no external funding is stated; he is also employed by the Dutch central bank. The paper itself flags that the IEA baseline relies on proprietary datasets (IDC, Omdia, SemiAnalysis) that "cannot be easily validated" — so the carbon intensity input is unauditable. Nine companies were reviewed; ByteDance and CoreWeave publish no environmental data at all. The author disputes the IEA's own indirect water intensity of 1.04 L/kWh, citing Meta data implying 3.92 L/kWh (~4x higher), and uses the higher figure.

## Relation to existing corpus

Resolves an unsourced claim. The repository README (line 9) asserts "AI's 2025 GHG footprint is estimated at ~80 million tonnes CO2e (comparable to New York City)" with no supporting file anywhere in `research/`. This is that source. The README statement is defensible only if rewritten as a range (32.6-79.7 Mt), operational-only, and attributed to de Vries-Gao 2025. As currently written it presents an upper bound as a central estimate. No prior excerpt cites de Vries-Gao.

---
Retrieved: 2026-09-19
Search: WebSearch "origin of 80 million tonnes CO2e AI 2025 emissions New York City" -> PMC full text
