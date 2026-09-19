# Across 46 models and 1,858 configurations on H100 and B200, task type alone changes inference energy 25x and GPU utilisation another 3–5x

**Topic:** Frugal AI — how comparable published AI energy figures actually are; sources of variance
**Source:** Chung, Wu, Ma & Chowdhury (University of Michigan; ML.ENERGY project), 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2601.22076
**Published:** 2026-01-29 (v2 2026-01-30)

## Finding

A measurement sweep of 46 generative models across 7 tasks and 1,858 configurations on NVIDIA H100 and
B200 GPUs finds order-of-magnitude variation inside the same model: LLM task type alone changes energy up
to 25x, video generation can exceed image generation by more than 100x, and differences in GPU
utilisation alone produce 3–5x. The authors argue that measurement without diagnosis is not actionable
and give a framework attributing time and energy to latent metrics — memory footprint and utilisation —
that are in turn set by choices across the algorithm, software and hardware layers. The framework extends
to throughput per watt, the metric that matters when a datacenter is power-constrained rather than
capital-constrained.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Scope | 46 models, 7 tasks, 1,858 configurations | NVIDIA H100 and B200 |
| Energy spread from LLM task type | up to 25x | Same model, different task |
| Video vs image generation | sometimes >100x | Generative AI beyond text |
| Energy spread from GPU utilisation | 3–5x | Utilisation as a latent variable |
| Causal chain proposed | algorithm / software / hardware → memory and utilisation → time and energy | Framework, not a single number |
| Derived metric | throughput per watt | For power-constrained datacenters |

## Methodology

Direct measurement in deployment-representative environments, continuing the ML.ENERGY Benchmark line of
work from the same group. B200 is included, so this is one of the few 2026 sources with measured
next-generation datacenter GPU energy rather than analytical projection. The contribution beyond the
numbers is the attribution framework: rather than reporting that configuration A beats configuration B,
it identifies memory and utilisation as the mediating variables, which is what makes a result transfer
to a configuration that was not measured.

Boundary is GPU energy on the serving node. No PUE, no full-datacenter overhead.

## Limitations and conflicts

Academic (University of Michigan); ML.ENERGY publishes a public leaderboard, which is both the credential
and the interest — its figures are cited by other parties in a live dispute over whether public inference
energy estimates are too high (see /research/frugal/017, where Microsoft authors use ML.ENERGY
measurements as their validation set while arguing that benchmark-derived numbers overstate production
energy by 4–20x). The variance reported here is the strongest available evidence that both sides can be
arithmetically correct: a 25x task effect and a 3–5x utilisation effect are together enough to span the
disputed range without anyone miscounting.

The practical consequence for this corpus: any single "Wh per query" figure, including those already in
these files, is a point estimate drawn from a distribution at least an order of magnitude wide, and
figures from different sources are not comparable unless task, configuration, utilisation and boundary all
match. Very few published figures state all four.

## Relation to existing corpus

No direct overlap. It supplies the comparability caveat that every per-query number elsewhere in the
corpus needs, including /research/frugal/017 (Oviedo et al.), /research/frugal/019 (Manya et al.),
/research/frugal/021 (Delavande et al.) and /research/community/001-luccioni-2024-power-hungry-ai.md. The
repo has no MLPerf Power excerpt; MLPerf Inference v6.0 (April 2026) and v6.1 (September 2026) both
carry an optional power category, but MLCommons does not normalise energy to service units such as joules
per generated token, which is the gap this measurement line addresses.

---
Retrieved: 2026-09-19
Search: arXiv abs:"H100" AND abs:"energy" AND (abs:"B200" OR abs:"Blackwell"); MLCommons v6.0/v6.1 results pages
