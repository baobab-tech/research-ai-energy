# Corrected record: "Efficiency Is Not Enough" argues compute efficiency does not imply energy or carbon efficiency, and documents an 88x disagreement between two published estimates of the same model

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
estimate was argued down by an author at the company whose model was being estimated — the paper does not
adjudicate between them, and neither should a reader.

## Relation to existing corpus

**This excerpt supersedes /research/ghg/018-wright-2025-efficiency-not-enough.md and
/research/water/023-wright-2025-efficiency-not-enough-sustainable-ai.md.** Both were written from the
abstract and the ACM landing page without the full text, and both state so ("Full paper needed",
"Likely addresses"). Specific corrections:

1. **Authorship is wrong in both.** There are four authors, not three: Dustin Wright, Christian Igel,
   Gabrielle Samuel and **Raghavendra Selvan** (Copenhagen), who is omitted.
2. **The central claim is misstated.** Both existing files say the paper argues that "systemic factors
   (scale of deployment, rebound effects, growth in AI usage) may overwhelm efficiency gains". The paper's
   first and most developed discrepancy is measurement-level, not scale-level: compute efficiency is not
   energy efficiency is not carbon efficiency. Scale/growth is not one of the three discrepancies.
3. **Rebound is discrepancy 2 of 3, not the thesis**, and it is argued rather than measured.
4. **Date.** The work is a 2023 preprint (v2 March 2025) published in CACM in 2025; describing it as a
   "2025 paper" obscures that it predates the reasoning-model era it is now cited against.
5. The ghg/018 entry's claim that "6 citations already in 2025 suggests emerging influence" is not a
   finding about the paper and should not have been in a Key Data section.

On the substance the corpus needs for its Jevons question: this paper does not supply 2026 empirical
support. Within this folder, the nearest thing to a mechanism-level argument for why efficiency will not
close the gap is /research/frugal/020 (Zhai et al. 2026), which proves over-thinking is structural in
reasoning-model reward design, and /research/frugal/017, where Microsoft authors concede the rebound
point in a single unmodelled paragraph. A 2026 position paper making the same case for reasoning models
specifically — Wiesner, O'Neill, Larosa & Kao, "Efficiency Will Not Lead to Sustainable Reasoning AI",
https://arxiv.org/abs/2511.15259 — was reviewed and not written up: it is assertion without new data, the
same weakness this correction is fixing.

---
Retrieved: 2026-09-19
Search: WebSearch "Wright Igel Samuel Efficiency Is Not Enough sustainable AI arXiv full text"; full PDF retrieved from arxiv.org/pdf/2309.02065 and read in full
