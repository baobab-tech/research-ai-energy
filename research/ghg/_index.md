# GHG Emissions Index

## Training & Inference
| # | Source | Insight | Link |
|---|--------|---------|------|
| 001 | Jiang et al., 2024 | LLM chatbots require full lifecycle carbon accounting beyond just training | [file](001-jiang-2024-llm-chatbot-lifecycle-footprint.md) |
| 002 | Li et al., 2025 | AI has a "secret water footprint" from data center cooling often overlooked in emissions analysis | [file](002-li-2025-ai-water-footprint.md) |
| 003 | Markelius et al., 2024 | Current AI hype is "historically unmatched" in planetary costs, exerting tremendous pressure on resources | [file](003-markelius-2024-ai-hype-costs.md) |
| 004 | Raiaan et al., 2024 | LLMs grew from millions to trillions of parameters "in a very short time" - exponential compute growth | [file](004-raiaan-2024-llm-challenges.md) |
| 005 | Wang et al., 2024 | AI reduces ecological footprints at macro level, but industrial structure moderates benefits | [file](005-wang-2024-ai-ecological-footprint-67-countries.md) |
| 006 | Berthelot et al., 2025 | First systematic study of environmental impact of deployed generative AI services (inference) | [file](006-berthelot-2025-environmental-impact-genai-services.md) |
| 018 | Wright, Igel & Samuel, 2025 | "Efficiency is not enough" - argues efficiency-first approach insufficient for sustainable AI | [file](018-wright-2025-efficiency-not-enough.md) |
| 019 | Dauner & Socher, 2025 | Empirical LLM energy measurement: 14 models tested, accuracy-emissions trade-off quantified | [file](019-dauner-2025-energy-costs-communicating-ai.md) |
| 020 | Rozycki et al., 2025 | Review finds embodied emissions often eclipse operational - dual strategy needed | [file](020-rozycki-2025-energy-aware-ml-models-review.md) |
| 021 | Kachris, 2025 | Hardware accelerator survey: GPUs, FPGAs, custom ASICs for LLM energy efficiency | [file](021-kachris-2025-hardware-accelerators-llm-survey.md) |

## Lifecycle & Embodied Emissions
| # | Source | Insight | Link |
|---|--------|---------|------|
| 007 | Istrate et al., 2024 | Digital content consumption analysis including embodied + operational emissions | [file](007-istrate-2024-digital-content-environmental-sustainability.md) |
| 008 | Barbierato & Gatti, 2024 | Hardware innovations key factor in environmental footprint; Red vs Green AI paradigms | [file](008-barbierato-2024-green-ai-methodological-survey.md) |
| 009 | Raman et al., 2024 | Sustainability must be integrated into "AI development lifecycle" | [file](009-raman-2024-green-sustainable-ai-thematic-analysis.md) |
| 010 | Zanoletti et al., 2024 | Li-ion battery recycling review - relevant to data center energy storage | [file](010-zanoletti-2024-lithium-ion-battery-recycling.md) |
| 011 | Psarommatis & May, 2024 | Digital Product Passport for tracking computing hardware lifecycle/circularity | [file](011-psarommatis-2024-digital-product-passport-circularity.md) |

**Key Gap**: No specific GPU/chip manufacturing emissions data in 2024-2025 literature.

## Numbers Compilation
| # | Source | Insight | Link |
|---|--------|---------|------|
| 012 | Li et al., 2023 | GPT-3 training: 700K liters water; ChatGPT: 500ml per 20-50 queries; 4.2-6.6B m³ global AI water by 2027 | [file](012-li-2023-making-ai-less-thirsty-water-numbers.md) |
| 013 | Tomlinson et al., 2024 | AI text generation 130-1500x less CO2e per page than humans; illustration 310-2900x less - with rebound effect caveats | [file](013-tomlinson-2024-ai-vs-human-emissions-comparison.md) |
| 014 | Chien et al., 2023 | CarbonMin request routing strategy can reduce inference emissions; 106 citations on carbon-aware scheduling | [file](014-chien-2023-genai-inference-carbon-reduction.md) |
| 015 | Jouppi et al. (Google), 2023 | TPU v4: 2-6x less energy, ~20x less CO2e than on-premise DSAs; 351 citations | [file](015-tpu-v4-energy-efficiency-numbers.md) |
| 016 | Verdecchia et al., 2023 | Green AI systematic review: energy savings up to 115%, 50%+ common; 205 citations | [file](016-verdecchia-2023-green-ai-systematic-review-savings.md) |
| 017 | Wang et al., 2023 | BERT fine-tuning energy varies by task, dataset, hardware; aggregate fine-tuning may rival pre-training | [file](017-wang-2023-bert-finetuning-energy-carbon.md) |

## Authoritative Aggregates — Agency & Primary Data (added 2026-09-19)
| # | Source | Insight | Link |
|---|--------|---------|------|
| 022 | de Vries-Gao, 2025 (Patterns) | Origin of the "~80 Mt CO2e" claim: actual range is 32.6-79.7 MtCO2, operational only; 80 Mt is the upper bound | [file](022-de-vries-gao-2025-ai-carbon-water-footprint.md) |
| 023 | IEA, 2025 (*Energy and AI*) | Data centres 415 TWh in 2024 (1.5% of global); ~945 TWh by 2030; 2035 scenarios span 700-1,700 TWh | [file](023-iea-2025-energy-and-ai-datacentre-electricity.md) |
| 024 | IEA, 2026 (*Key Questions on Energy and AI*) | 485 TWh in 2025, ~950 TWh by 2030; first IEA CO2 figure: ~350 Mt by 2035 (~2% of power-sector emissions) | [file](024-iea-2026-key-questions-energy-ai.md) |
| 025 | Shehabi et al., LBNL 2024 | US data centres 176 TWh in 2023 (4.4% of US electricity); 2028 range 325-580 TWh (6.7-12.0%); see datacenters/016 for the 2026 update | [file](025-shehabi-2024-lbnl-us-data-center-energy.md) |
| 026 | Oviedo et al. (Microsoft), 2026 (Joule) | 0.31 Wh median per frontier-model query (IQR 0.16-0.60), full-node and PUE-inclusive; 3.91 Wh under test-time scaling | [file](026-oviedo-2026-per-query-inference-energy.md) |
| 027 | Schneider et al. (Google), 2025 | First published AI-accelerator manufacturing emissions: 386-692 kgCO2e embodied per TPU chip; operational still 70-90% of lifetime | [file](027-schneider-2025-tpu-lifecycle-embodied-emissions.md) |
| 028 | Google, 2026 Environmental Report | Reports 14.5 MtCO2e for 2025, but location-based Scope 2 alone is 15.1 Mt — a 12.3 Mt accounting gap; electricity +37% | [file](028-google-2026-environmental-report-accounting-gap.md) |
| 029 | Microsoft, 2026 Sustainability Report | FY2025 total 21.1 MtCO2e (+26%); Scope 2 market-based rose 10.4x after dropping non-additional RECs; location-based 12.0 Mt | [file](029-microsoft-2026-sustainability-report-fy25.md) |
| 030 | Guidi et al., 2026 | 403 US hyperscale sites: 68-99 TWh and 37-54 MtCO2; carbon intensity 545 gCO2/kWh, 48% above US grid average | [file](030-guidi-2026-us-hyperscale-carbon-intensity.md) |
| 031 | EIA, 2026 (AEO2026 + Sep STEO) | Data-centre servers now modelled separately: ~7% of US commercial electricity in 2025, 22-33% by 2050 | [file](031-eia-2026-data-center-electricity-outlook.md) |
| 032 | Epoch AI / Stanford AI Index, 2026 | Grok 4 training: 72,000 tCO2e (AI Index) vs ~154,000 tCO2e (Epoch, 310 GWh on gas turbines) — a 2x disagreement | [file](032-epoch-2026-grok4-training-emissions.md) |

**Gap closed**: 027 supplies the GPU/chip manufacturing emissions data previously flagged as missing (for TPUs; no GPU equivalent has been published by NVIDIA).

**README correction needed**: the claim "AI's 2025 GHG footprint is estimated at ~80 million tonnes CO2e" quotes the upper bound of de Vries-Gao's 32.6-79.7 Mt range as if it were a central estimate. See 022.
