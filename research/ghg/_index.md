# GHG Emissions Index

21 excerpts, every one verified against its source. Summary in [README.md](README.md).

| # | Source | Finding |
|---|--------|---------|
| 001 | [Jiang et al., 2024](001-jiang-2024-llm-chatbot-lifecycle-footprint.md) | Eight-phase lifecycle framing for chatbots, with ChatGPT service electricity modelled at up to 7.128 TWh/year |
| 006 | [Berthelot et al., 2025](006-berthelot-2025-environmental-impact-genai-services.md) | Full-service LCA puts one year of Stable Diffusion at 463 t CO2e, with terminals and networks at 45% of it |
| 007 | [Istrate et al.](007-istrate-2024-digital-content-environmental-sustainability.md) | A full-boundary LCA puts data-centre operation at 20-30% of the climate impact of consumer digital services, behind end-user device manufacturing at 32% |
| 012 | [Li et al., 2023](012-li-2023-making-ai-less-thirsty-water-numbers.md) | Carbon-optimal and water-optimal training schedules conflict: siting LaMDA where solar is abundant minimises CO2e and maximises evaporation |
| 013 | [Tomlinson et al., 2024](013-tomlinson-2024-ai-vs-human-emissions-comparison.md) | AI writing emits 130-1500x less CO2e per page than a human, against a baseline that charges the writer a pro-rata share of their entire annual lifestyle footprint |
| 014 | [Chien et al., 2023](014-chien-2023-genai-inference-carbon-reduction.md) | ChatGPT-scale inference modelled at 25x the training emissions of GPT-3, with carbon-aware routing cutting 35% |
| 015 | [Jouppi et al., 2023](015-tpu-v4-energy-efficiency-numbers.md) | TPU v4 in Google Cloud: 2.85x less energy and 18.3x less operational CO2e than a hypothetical on-premise accelerator, with 6.4x of that ratio coming from market-based electricity accounting |
| 016 | [Verdecchia et al., 2023](016-verdecchia-2023-green-ai-systematic-review-savings.md) | Green AI savings across 98 studies: only 27 report a number at all, median 53%, and the often-quoted 115% is a single unexplained outlier |
| 017 | [Wang et al.](017-wang-2023-bert-finetuning-energy-carbon.md) | One BERT pre-training run costs 368 kWh, equal to between 392 and 45,109 fine-tuning runs depending on the task |
| 019 | [Dauner & Socher, 2025](019-dauner-2025-energy-costs-communicating-ai.md) | Measured on one A100: 14 open-weight LLMs span 27.7 to 2,042 gCO2e for the same 1,000 questions, a 74x spread driven by reasoning token output rather than parameter count |
| 020 | [Różycki et al., 2025](020-rozycki-2025-energy-aware-ml-models-review.md) | A narrative review whose claim that embodied emissions "eclipse" operational rests on a single cross-boundary comparison: all IT equipment manufactured worldwide versus ML training alone |
| 022 | [Vries-Gao, 2025](022-de-vries-gao-2025-ai-carbon-water-footprint.md) | AI data centres emitted 32.6-79.7 MtCO2 in 2025 — the origin of the "80 million tonnes" figure |
| 023 | [IEA, 2025](023-iea-2025-energy-and-ai-datacentre-electricity.md) | IEA baseline: data centres used 415 TWh in 2024 (1.5% of global electricity), projected to ~945 TWh by 2030 |
| 024 | [IEA, 2026](024-iea-2026-key-questions-energy-ai.md) | IEA 2026 update: data centres consumed 485 TWh in 2025, on track to ~950 TWh by 2030, with CO2 reaching ~350 Mt by 2035 |
| 026 | [Oviedo et al., 2026](026-oviedo-2026-per-query-inference-energy.md) | Microsoft authors estimate 0.31 Wh per frontier-model query (IQR 0.16-0.60), full-node and PUE-inclusive, and claim public figures are 4-20x too high |
| 027 | [Schneider et al., 2025](027-schneider-2025-tpu-lifecycle-embodied-emissions.md) | First published manufacturing emissions for an AI accelerator: 386-692 kgCO2e embodied per TPU chip over six years; operational still dominates at 70-90% |
| 028 | [Google, 2026](028-google-2026-environmental-report-accounting-gap.md) | Google's reported 2025 footprint is 14.5 MtCO2e, but its location-based Scope 2 alone is 15.1 Mt — the accounting choice hides 12.3 Mt |
| 029 | [Microsoft, 2026](029-microsoft-2026-sustainability-report-fy25.md) | Microsoft FY2025 emissions rose 26% to 21.1 MtCO2e; Scope 2 market-based jumped 10x after it stopped buying non-additional RECs |
| 030 | [Guidi et al., 2026](030-guidi-2026-us-hyperscale-carbon-intensity.md) | 403 US hyperscale data centres drew 68-99 TWh and emitted 37-54 MtCO2 in one year, at a carbon intensity 48% above the US grid average |
| 031 | [EIA, 2026](031-eia-2026-data-center-electricity-outlook.md) | EIA now models data-centre servers separately: ~7% of US commercial electricity in 2025, rising to 22-33% by 2050 |
| 032 | [Epoch AI / Stanford AI Index, 2026](032-epoch-2026-grok4-training-emissions.md) | Two credible estimates of Grok 4's training emissions differ by 2x (72,000 vs 154,000 tCO2e) — and both are 14-30x GPT-4 |
