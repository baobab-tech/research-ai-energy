# Production-scale LLM inference modelled at 0.31 Wh median per query, rising 13x under test-time scaling

**Topic:** Frugal AI — energy per query in production serving; the energy cost of test-time compute
**Source:** Oviedo, Kazhamiaka, Choukse, Kim, Luers, Nakagawa, Bianchini & Lavista Ferres (all Microsoft), 2026
**Type:** peer-reviewed (Joule) / preprint
**URL:** https://arxiv.org/abs/2509.20241
**Published:** 2025-09-24 (v1); revised 2026-06-09; Joule (2026) 102430

## Finding

A bottom-up Monte Carlo model of frontier-scale (>200B parameter) LLM serving on 8xH100 nodes at FP8
gives a median 0.31 Wh per query (IQR 0.16–0.60), which the Microsoft authors use to argue that widely
cited public figures overstate inference energy by 4–20x because those figures assume unbatched,
non-production serving. The same model applied to a test-time-scaling regime — median 5,000 output
tokens instead of 300 — raises the median 13x to 3.91 Wh/query (IQR 2.15–7.05). At one billion
queries/day the baseline is 0.7 GWh/day; if 10% of queries are long, it becomes 1.7 GWh/day. The paper
claims 8–20x "line-of-sight" efficiency reductions are available, attributed mostly to distillation,
small models and routing rather than hardware.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Median energy, traditional query, >200B model | 0.31 Wh (IQR 0.16–0.60) | Full node (8xH100, FP8) x server/IT power x PUE; modelled, not measured |
| Median energy, test-time scaling query | 3.91 Wh (IQR 2.15–7.05) | Same; L_out median 5,000 tokens (IQR 2,040–9,717) |
| Traditional-regime output length assumed | median 300 tokens (IQR 129–618), L_in fixed 500 | Assumed distribution, not observed traffic |
| Node power P_node | log-normal centred on 0.7 x P_max; P_max 10.2 kW (8xH100) or 12.5 kW (10xH100, DeepSeek-R1) | Literature-reported ~70% average power utilisation |
| PUE | log-normal, P5–P95 1.05–1.40 | Hyperscaler public reports |
| Llama 3.1 405B | 0.39 Wh median estimate (IQR 0.19–0.68) | Compared against ML.ENERGY v3.0 measured median 0.21 Wh (GPU-only) |
| Mixtral 8x22B | 0.06 Wh median estimate (IQR 0.03–0.11) | ML.ENERGY measured 0.11 Wh at FP8-normalised |
| Datacenter scale, 1B queries/day | 0.7 GWh/day baseline; 1.7 GWh/day at 10% long queries; 0.8 GWh/day with interventions | Derived from the per-query distribution |
| Claimed available efficiency headroom | 8–20x | "Line-of-sight", assembled from literature, not demonstrated end to end |

## Methodology

E_query = (P_node x PUE / 3.6) x (L_eff / TPS) x alpha. Nothing here is a new measurement. Node power,
PUE and output length are each sampled as distributions (10,000 draws); token throughput TPS comes from
a piecewise log-linear regression fitted to published NVIDIA TensorRT-LLM benchmark data for five models
(DeepSeek-R1 671B, Llama 3.1 405B, Nemotron Ultra 253B, Mixtral 8x22B, Llama 3.1 70B) under tensor
parallelism 8 and continuous batching. The system boundary is deliberately wider than most published
measurements: full node including CPU and non-GPU IT, multiplied by PUE. That makes the headline number
*higher* than a GPU-only measurement of the same workload, so the 4–20x "overestimation" claim is not a
boundary artefact — it turns on batching and concurrency assumptions, not on what is counted.

Validation is by comparison against third-party measured values (ML.ENERGY leaderboard, Caravaca et al.),
which fall inside the modelled IQR for all compiled cases but one.

## Limitations and conflicts

All eight authors are Microsoft employees; the declaration of interests says so explicitly. The paper's
central rhetorical move — that public estimates are 4–20x too high and that "alarmist claims drawn from
narrow benchmarks should be avoided" — directly serves the commercial interest of a hyperscaler facing
scrutiny over datacenter energy. The specific targets named are the IEA's per-query estimates (~1.25 Wh
for Mixtral 8x22B, ~2.25 Wh for DeepSeek-R1) and the AI Energy Score (~1.01 Wh FP8-normalised for
Llama 3.1 70B). Read as an argument about serving assumptions it is substantiated; read as a measurement
of Microsoft's own fleet it is not one, and no Microsoft production data appears in the paper.

Self-declared limitations: single-node only, so inter-node orchestration, ramp-up and network are
excluded; idealised token-length distributions; prefill cost for long-context queries understated (the
authors flag agentic coding and multi-document summarisation as the weak cases); TPS held at a plateau
beyond 4,000 output tokens rather than declining, which understates energy for very long generations;
text generation only, excluding image and video. Agentic workflows are modelled as a sum of independent
queries, with tool calling and context management explicitly out of scope.

The discussion section concedes the rebound argument in one paragraph — "efficiency gains do not
guarantee lower absolute energy use" — without modelling it, so the 8–20x headroom figure should not be
read as a projection of fleet energy.

## Relation to existing corpus

**Same source as /research/ghg/026-oviedo-2026-per-query-inference-energy.md**, written in parallel during
the same 2026-09-19 refresh. That file treats the paper as a per-query emissions figure and interrogates
its system boundary. This file treats it as the efficiency-headroom and test-time-compute source it also
is: the 13x test-time-scaling multiplier, the 8–20x claimed headroom and its attribution to distillation
and routing rather than hardware, the Monte Carlo construction of the TPS model, and the unmodelled
rebound concession. Read the ghg file for the boundary argument; read this one for what the paper claims
efficiency can still deliver. Neither should be cited without the other.

Otherwise no overlap. This is the first excerpt in the frugal folder covering test-time compute energy,
and the first production-serving per-query energy model. It contradicts the boundary of the per-prompt figures
used elsewhere in the corpus (e.g. /research/frugal/027-luccioni-2024-power-hungry-processing.md), whose
unbatched measurement conditions are exactly what this paper argues against. It also complements
/research/frugal/012-stojkovic-2025-dynamollm-energy-efficient-inference.md, which shares a co-author
(Choukse) and the same Microsoft Azure research group.

---
Retrieved: 2026-09-19
Search: arXiv all:"energy per token" sortBy=submittedDate; cross-checked via web search "MLPerf Inference v6.0 2026 power results"
