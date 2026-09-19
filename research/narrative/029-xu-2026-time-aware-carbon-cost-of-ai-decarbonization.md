# Assessments of AI-enabled decarbonisation report physical-system savings while omitting AI-side emissions and the lag between cost and benefit

**Topic:** narrative — what a defensible avoided-emissions calculation for AI would have to include
**Source:** Chenrui Xu, Burcu Akinci, Christopher McComb (Carnegie Mellon University), 2026
**Type:** preprint (accepted, ASCE International Conference on Computing in Civil Engineering i3CE 2026)
**URL:** https://arxiv.org/abs/2609.18029
**Published:** 2026-09-16

## Finding

Two structural omissions are identified in existing assessments of AI-enabled decarbonisation in the built environment: AI-side emissions from development, training and use are left out, and the temporal mismatch between when AI's carbon cost is incurred and when the physical benefit materialises is ignored. The authors formalise both as discrete-time streams — avoided emissions S(t) and AI-induced emissions C(t) over a finite horizon — and show that with a 3% carbon discount rate applied, the preferred ranking among candidate interventions reverses relative to undiscounted totals. Interventions whose benefits are back-loaded (infrastructure-scale projects, where AI cost is a build-phase lump and savings accrue over decades) lose to interventions with earlier benefits, even when their undiscounted totals are larger.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Discount rate in worked examples | 3% | Applied uniformly; emissions factors treated as exogenous |
| Assessment horizon | H = 10 years | — |
| Interventions compared | 4 | Low-carbon concrete design support; AI-assisted construction logistics; agentic HVAC control; predictive maintenance |
| Decision metrics defined | discounted return on carbon R; net emissions present value NEPV; discounted carbon payback t_payback; break-even discount rate | Eqs. 1–5 |
| Effect of discounting | Ranking reversal between the two build-phase cases and between the two use-phase cases | Break-even discount rates computed for each pair |
| Use-phase comparison | Break-even on the efficiency ratio at r ≈ 8.2%, but on net impact at a much smaller rate — so "even modest discounting may favor the earlier-benefit HVAC-control case" | Stylised streams |

## Methodology

A framework paper with stylised demonstrations. All four intervention profiles are constructed by the authors to have deliberately different temporal shapes; the numbers in Tables 1 and 2 are illustrative inputs, not measurements of real deployments. Nothing here is evidence that any particular AI intervention does or does not pay back its carbon cost.

What the paper establishes is a requirement: an avoided-emissions claim for AI is incomplete unless it states C(t) alongside S(t) and specifies the horizon and the time preference. Measured against that requirement, none of the major published claims qualifies. The IEA's 1 400 Mt for 2035 (`narrative/021-iea-2025-energy-and-ai-avoided-emissions-scenario.md`) states neither C(t) nor a horizon-discounting treatment. Google's 41 Mt (`narrative/022-google-2026-enabled-emissions-41mt.md`) nets AI compute cost against benefit in exactly one of nine product lines — the contrails model, 380 tCO2e against 3 000 tCO2e — and omits it for the other eight, including the 27.8 Mt Google Earth line. The accounting setup is ISO 14040/14044-aligned.

## Limitations and conflicts

Preprint of an 8-page conference paper; the contribution is a framework plus decision heuristics, not empirical results. A constant discount rate applied uniformly to carbon is itself a contested modelling choice — discounting future emissions reductions embeds a value judgement about intergenerational weighting that the paper acknowledges by computing break-even rates but does not resolve. Emissions factors are exogenous, so grid decarbonisation over the horizon is not endogenised, which biases against late-benefit interventions independently of the discount rate. Carnegie Mellon authors in civil and mechanical engineering; no funding statement or industry affiliation is disclosed in the preprint.

## Relation to existing corpus

No direct overlap. Complements `narrative/023-okeeffe-brander-2026-avoided-emissions-methodology-comparison.md`: that paper shows existing protocols disagree on what to calculate; this one adds a component — the temporal profile of AI-induced emissions — that none of them includes.

---
Retrieved: 2026-09-19
Search: arXiv `all:"avoided emissions"`, submissions since 2025-09; full PDF retrieved and text-extracted
