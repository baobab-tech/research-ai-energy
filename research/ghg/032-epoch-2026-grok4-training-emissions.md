# Two credible estimates of Grok 4's training emissions differ by 2x (72,000 vs 154,000 tCO2e) — and both are 14-30x GPT-4

**Topic:** GHG emissions — training-run emissions for 2025-2026 frontier models and the dispersion between estimates
**Source:** Epoch AI, "What did it take to train Grok 4?"; Stanford HAI, *AI Index Report 2026*
**Type:** dataset / analysis (Epoch); agency-style index report (Stanford HAI)
**URL:** https://epoch.ai/data-insights/grok-4-training-resources
**Source note:** https://spectrum.ieee.org/state-of-ai-index-2026
**Published:** 2026 (Epoch data insight); AI Index 2026

## Finding

No 2025-2026 frontier training run has disclosed emissions, so every figure is an outside estimate, and the two most credible ones for xAI's Grok 4 disagree by a factor of two: Stanford's AI Index puts it above 72,000 tCO2e, Epoch AI at ~154,000 tCO2e (elsewhere cited as ~140,000-150,000). The disagreement is not about compute so much as about what powers the compute — xAI's Colossus site in Memphis ran substantially on mobile natural-gas turbines at ~0.49 kgCO2e/kWh, roughly 1.3x the US grid average, which Epoch applies directly. Either figure is an order of magnitude above GPT-4 (5,184 tCO2e) and Llama 3.1 405B (8,930 tCO2e) as estimated in the same AI Index.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Grok 4 compute | 246 million H100-hours | Epoch, from xAI public statements |
| Grok 4 electricity | 310 GWh | 700 W peak x 75% utilisation x 2.03 non-GPU multiplier x 1.2 cooling/power multiplier |
| Grok 4 CO2e — Epoch | ~154,000 t | 310 GWh x 0.49 kgCO2e/kWh (on-site natural gas) |
| Grok 4 CO2e — Stanford AI Index | >72,000 t | Different, unstated grid assumption |
| Grok 4 water | 750 million L | 158 gal/MWh generation + 1.8 L/kWh data centre |
| Grok 4 cost | ~USD 490 m | H100 rental $1.90-2.20/hr, or depreciation + $0.08-0.20/kWh |
| GPT-4 training | 5,184 tCO2e | AI Index |
| Llama 3.1 405B training | 8,930 tCO2e | AI Index |
| Grok 4 / GPT-4 ratio | 14x (AI Index) to 30x (Epoch) | |
| Assumed grid intensity, Memphis gas turbines | 0.49 kgCO2e/kWh | ~1.3x US grid average |

## Methodology

Epoch's chain is: public xAI statements -> GPU-hours -> peak power at 700 W -> derate to 75% of peak -> multiply 2.03x for non-GPU hardware -> multiply 1.2x for power and cooling overhead -> multiply by an emission factor. Every step is an assumption; none is measured. Epoch propagates uncertainty using log-normal distributions with 90% confidence intervals rather than point estimates, and states that "significant uncertainty" around the GPU-hour input cascades through everything downstream. This is a training-run boundary only: it excludes experiments and failed runs preceding the final run, embodied hardware emissions, and all subsequent inference.

## Limitations and conflicts

Neither figure is from the model developer; xAI has disclosed nothing. Stanford's AI Index co-director Ray Perrault states the Grok estimates "rely heavily on inferred inputs drawn from public reporting (e.g., *Forbes* articles), xAI statements, and other non-verifiable sources." The AI Index does not publish its derivation, which is why the 2x gap with Epoch cannot be adjudicated. Epoch AI is philanthropically funded and publishes compute estimates used across the field; it is not independent of the AI-forecasting discourse it informs. The 0.49 kgCO2e/kWh factor assumes the gas-turbine configuration persisted through the training run — a point on which reporting is contested, and it drives the entire difference between the two estimates.

## Relation to existing corpus

No direct overlap; the corpus has no post-2024 training-run figures. Extends the training-cost line running from `research/ghg/001-jiang-2024-llm-chatbot-lifecycle-footprint.md`. The dispersion here is the counterpoint to 026: per-query inference estimates are converging within an IQR, while training-run estimates for undisclosed runs still differ by 2x.

---
Retrieved: 2026-09-19
Search: WebSearch "2026 training compute carbon emissions frontier model tCO2e Epoch AI"; WebFetch epoch.ai and spectrum.ieee.org
