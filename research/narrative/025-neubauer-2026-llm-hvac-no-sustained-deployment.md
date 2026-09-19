# Of 66 studies on LLMs for HVAC operations, four reach pilot-level evidence and none reports a sustained operational deployment

**Topic:** narrative — is there measured, at-scale evidence for AI energy savings in buildings?
**Source:** Alexander Neubauer, Tianzhen Hong, Han Li, Mengbo Yu, Amin Darbandi, Yannick Fürst, Martin Kriegel, 2026
**Type:** preprint (systematic review, submitted to *Energy and Buildings*)
**URL:** https://arxiv.org/abs/2609.05314
**Published:** 2026-09-04

## Finding

Buildings HVAC optimisation is one of the five mechanisms the IEA counts toward its 1 400 Mt avoided-emissions scenario, at an assumed ~10% energy saving. This systematic review of 66 peer-reviewed studies on large language models for HVAC operations, published 2023 to March 2026, finds the underlying evidence base does not support deployment claims: only four studies reach pilot-level evidence, none reports sustained operational deployment, and no study was classified as ready for industry adoption. Sixty-three of 66 were classified research-only and three near-term. The authors' conclusion is that current evidence supports LLMs "primarily as semantic and workflow layers rather than autonomous HVAC controllers."

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Studies coded | 66 | Peer-reviewed, 2023 – March 2026 |
| Studies reaching pilot-level evidence | 4 | Authors' evidence-realism scale |
| Studies reporting sustained operational deployment | 0 | — |
| Deployment-readiness classification | 63 research-only, 3 near-term, 0 ready-now | Three-level scale |
| Concentration of the corpus | 32 of 66 in building energy modelling | Load forecasting "too sparse for subfield-level conclusions" |

## Methodology

Systematic review with explicit coding. Each study is classified across five application families and three LLM method families, then scored on three axes: evidence realism, deployment readiness, and the responsibility boundary between the LLM and physical HVAC decisions. The scoring is the contribution — most reviews in this area count papers by topic; this one grades them by how close the evidence is to a running building.

Scope caveat that matters for how this is used: the review covers **large language models** specifically. It does not cover conventional machine learning, model-predictive control, reinforcement learning, or ontology-based tools, which the authors state "remain more adopted for high-frequency control, short-horizon numerical forecasting, and well-posed ontology mapping." The finding is therefore not that no AI method controls HVAC anywhere — it is that the generative-AI wave specifically has produced no documented sustained deployment, while the older methods that do have deployments predate the current AI buildout and do not require it.

## Limitations and conflicts

Preprint, not yet through peer review. Author affiliations span Lawrence Berkeley National Laboratory (Hong, Li, Yu) and TU Berlin (Neubauer, Darbandi, Fürst, Kriegel); no funding conflict is evident, and LBNL's building-technologies group has no commercial stake in the result. Publication bias runs against the finding rather than for it — the literature reviewed is written by researchers with an incentive to report successes, and it still contains no sustained deployment, which strengthens the negative result. The review cannot rule out unpublished proprietary deployments inside vendors or operators; it establishes only that none is documented in the peer-reviewed record.

## Relation to existing corpus

No direct overlap. Supplies the deployment-evidence test for one of the five IEA mechanisms in `narrative/021-iea-2025-energy-and-ai-avoided-emissions-scenario.md`. Related in spirit to `narrative/010-alzoubi-2024-green-ai-initiatives-validation-gap.md` (55 green-AI initiatives, most lacking empirical validation) and `narrative/020-ai-wastewater-treatment-limits-2025.md` (AI in wastewater mostly predictive studies, real deployments limited), but this is a newer, harder-coded instance in a sector the avoided-emissions scenarios depend on.

---
Retrieved: 2026-09-19
Search: arXiv `abs:"reinforcement learning" AND abs:"HVAC" AND abs:"deployment"`, submissions since 2025-09
