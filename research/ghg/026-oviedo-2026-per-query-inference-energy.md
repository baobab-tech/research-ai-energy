# Microsoft authors estimate 0.31 Wh per frontier-model query (IQR 0.16-0.60), full-node and PUE-inclusive, and claim public figures are 4-20x too high

**Topic:** GHG emissions — per-query inference energy, system boundary and production vs benchmark settings
**Source:** Oviedo, Kazhamiaka, Choukse, Kim, Luers, Nakagawa, Bianchini, Lavista Ferres — all Microsoft, 2026
**Type:** peer-reviewed (Joule) with open preprint
**URL:** https://arxiv.org/abs/2509.20241
**Source note:** published version: https://www.cell.com/joule/fulltext/S2542-4351(26)00114-5
**Published:** preprint 2025-09-24; Joule 2026

## Finding

For models above 200B parameters served on 8xH100 nodes at FP8 with production optimisations (dynamic batching, KV cache, TensorRT-LLM), the estimated median energy is 0.31 Wh per query, IQR 0.16-0.60. The boundary matters and is stated: this is **full-node** energy (not accelerator-only) **multiplied by PUE**, which makes it the more inclusive boundary, yet the number is lower than most published figures. The authors attribute the gap to benchmark settings — small batch, low concurrency, FP16 — rather than to boundary differences. Under test-time scaling (5,000 median output tokens instead of 300) the median rises 13x to 3.91 Wh (IQR 2.15-7.05).

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Frontier-scale (>200B params), standard query | 0.31 Wh median (IQR 0.16-0.60) | Full node, 8xH100, FP8, PUE-inclusive; 500 input / 300 median output tokens (IQR 129-618) |
| Test-time scaling query | 3.91 Wh median (IQR 2.15-7.05) | 5,000 median output tokens (IQR 2,040-9,717) |
| Llama 3.1 405B | 0.39 Wh median (IQR 0.19-0.68) | vs ML.ENERGY v3.0 measured 0.21 Wh (GPU-only) |
| Mixtral 8x22B | 0.06 Wh median (IQR 0.03-0.11) | vs ML.ENERGY 0.11 Wh (BF16 normalised to FP8) |
| DeepSeek-R1 (reasoning) | 10.6 Wh median (IQR 4.29-21.7) | vs ML.ENERGY 20.9 Wh at 11,287 avg output tokens |
| Non-production comparators | AI Energy Score ~1.01 Wh (Llama 3.1 70B, FP16->FP8 normalised); IEA ~1.25 Wh (Mixtral 8x22B), ~2.25 Wh (DeepSeek-R1) | No production optimisations |
| 1 bn queries/day | 0.7 GWh/day; 1.7 GWh/day if 10% long; 0.8 GWh/day with efficiency interventions | Datacentre scale |
| Headroom claimed | 8-20x line-of-sight energy reduction | Across models, serving systems, hardware |

## Methodology

Not a measurement. A bottom-up Monte Carlo estimate: Wh/query = (node power x time) / throughput x PUE, with 10,000 samples drawn over distributions of output length, node power and PUE. Token throughput comes from published NVIDIA TensorRT-LLM benchmark data for H100, not from the authors' own production fleet. The authors validate by checking whether independent production measurements fall inside their IQR — they mostly do (one ML.ENERGY value for Llama 3.1 70B falls slightly below). So the claim of validation rests on interval coverage, not on point agreement.

## Limitations and conflicts

Every author is a Microsoft employee, and Microsoft is among the largest operators whose per-query energy is under public scrutiny; the paper's central argument is that outside estimates of that energy are 4-20x too high. The declaration of interests states the analysis uses only open-source models and public disclosures — which is also the limitation: despite Microsoft's access to fleet telemetry, no proprietary production data was used, so the paper's authority derives from modelling assumptions rather than from privileged measurement. The estimate covers serving only; it excludes training amortisation, embodied hardware emissions, idle capacity provisioned but unused, and retrieval/tool calls in agentic workflows. Energy, not CO2 — no grid intensity is applied. The 8-20x "line-of-sight" reduction is a projection of announced or plausible improvements, not a demonstrated result.

## Relation to existing corpus

Directly relevant to `research/ghg/019-dauner-2025-energy-costs-communicating-ai.md`, which measured A100 hardware in a non-production single-query setting — exactly the class of estimate this paper argues is inflated. The two are not contradictory: Dauner and Socher measured what they measured; Oviedo et al. argue it does not represent at-scale serving. Also bears on the Google 0.24 Wh/prompt claim discussed in `research/water/017-google-2025-gemini-water-measurements.md`. The same paper is captured from the efficiency-pathways angle at `research/frugal/017-oviedo-2026-production-inference-energy-test-time-scaling.md`; this file records the per-query number and its system boundary.

---
Retrieved: 2026-09-19
Search: WebSearch "2026 measured energy per token LLM inference Wh full-stack PUE production"; arXiv PDF 2509.20241 extracted locally
