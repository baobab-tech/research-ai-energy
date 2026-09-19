# Compute efficiency does not imply energy efficiency, and neither implies carbon efficiency

**Topic:** Frugal AI — the limits of efficiency; rebound effects
**Source:** Wright, Igel & Selvan (University of Copenhagen) and Samuel (King's College London), 2023 preprint / 2025 CACM
**Type:** peer-reviewed (Communications of the ACM) — read here from the author preprint
**URL:** https://arxiv.org/abs/2309.02065
**Source note:** full text retrieved); journal version https://doi.org/10.1145/3724500
**Published:** arXiv v1 2023-09-05, v2 2025-03-22; CACM 2025

## Finding

The paper's argument is not that scale overwhelms efficiency — that is what the existing corpus entries
claim it says. It is that efficiency is measured against the wrong quantity at three separate points.
First, compute efficiency does not imply energy efficiency, which does not imply carbon efficiency:
parameter count and runtime are poor predictors of energy, and operational emissions depend on when and
where a job runs. Second, efficiency changes behaviour across the model life cycle, where deployment can
be ~90% of lifetime compute and where an efficiency gain in development licenses a broader hyperparameter
search — a rebound effect the authors say has been documented at multiple large companies. Third,
efficiency metrics do not capture embodied emissions, water, mining or e-waste at all. The proposed
alternative is systems thinking, not a rejection of efficiency work.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Deployment share of lifetime compute | can reach ~90% | Cited from prior work; varies with adoption and model lifetime |
| Disagreement between two published estimates of the same model | Patterson et al. argued Strubell et al.'s Evolved Transformer figure was ~88x too high | Difference in assumed model-selection settings and infrastructure, not arithmetic |
| Embodied share of emissions | ~10% for data centres; 40–80% for edge devices such as phones | Cited estimates |
| BLOOM (176B) embodied emissions | 22% of total, 11.2 t CO2eq | Luccioni et al., cited |
| GPT-3 (175B) training water | 700,000 L clean fresh water | Li et al. 2023, cited |
| Carbon intensity variability | Denmark, London and Edinburgh 2019–2023 show vastly different distributions, all high-variance with peaks | ElectricityMaps hourly data, plotted by the authors |
| Compute-vs-energy relationship | Parameter count and training time each fail to predict energy | Authors' own plots over the EC-NAS CNN dataset |

## Methodology

A perspective paper, not an empirical study. Its own analysis consists of plots over an existing dataset
(EC-NAS, CNNs with recorded energy) showing that parameter count and training time do not track energy,
plus hourly carbon-intensity distributions for three European regions from ElectricityMaps. Everything
else is a synthesis of published figures. The rebound claims are supported by citation to Patterson et
al. and Wu et al. reporting rebound at large companies, plus the Widdicks et al. systems-thinking
literature — not by new measurement.

So: the argument is reasoned and the supporting figures are real, but the paper contains **no empirical
test of a rebound effect in AI**. Anyone citing it as evidence that Jevons applies to AI is citing an
argument, not a measurement.

## Limitations and conflicts

Academic authors (Copenhagen, KCL); no industry funding disclosed. The paper is normative in intent and
selects supporting evidence accordingly. The 88x Strubell/Patterson disagreement is presented as
illustrating a transparency problem, which it does, but it is also a case where a large published
estimate was argued down by an author at the company whose model was being estimated. The paper does not
adjudicate between them, and neither should a reader.

## Relation to existing corpus

The paper's first discrepancy, that compute efficiency does not track energy efficiency, is
confirmed empirically by the sign reversals measured in
`021-delavande-2026-quantization-batching-serving-energy.md`,
`022-dutta-2026-speculative-decoding-energy.md` and
`023-alfarizy-2026-moe-sparsity-edge-energy.md`, where INT8, speculative decoding and MoE sparsity
each reduced a proxy metric while raising joules. Its second discrepancy, energy against carbon,
is the same accounting gap documented in `../washing/018-google-2026-market-vs-location-based-gap.md`.
The rebound argument is asserted in this paper without measurement; no empirical 2026 study of AI
rebound effects exists.

---
Retrieved: 2026-09-19
Search: WebSearch "Wright Igel Samuel Efficiency Is Not Enough sustainable AI arXiv full text"; full PDF retrieved from arxiv.org/pdf/2309.02065 and read in full
