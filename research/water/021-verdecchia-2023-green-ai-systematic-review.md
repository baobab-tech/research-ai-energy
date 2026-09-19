# Green AI Systematic Review: Only 27 of 98 Studies Report an Energy Saving at All, and the Reported Range Is Undefined

**Topic:** Energy — state of the Green AI research literature; reliability of reported efficiency savings
**Source:** Roberto Verdecchia (University of Florence), June Sallou, Luís Cruz (Delft University of Technology), 2023
**Type:** peer-reviewed (WIREs Data Mining and Knowledge Discovery 13(4), e1507)
**URL:** https://doi.org/10.1002/widm.1507
**Source note:** Wiley blocks automated requests; open preprint of the same text at https://arxiv.org/abs/2301.11047
**Published:** 2023-06

## Finding

Of 98 primary studies on Green AI, 27 report a concrete energy-saving percentage. Across those 27 the reported figures span 13% to 115%, and 17 report at least 50%. The 115% is a single data point from one study on neuron pruning in trained deep neural networks; the review neither defines the metric nor states the baseline any primary study measured against, so the range is a tally of incommensurable self-reported numbers rather than a synthesised effect size. A saving above 100% cannot be a fraction of a baseline consumption, so that figure uses some other denominator, which the review does not identify. The review also finds that 73 of 98 studies are laboratory experiments and 85 of 98 target academic readers, so these savings are largely not demonstrated in production.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Primary studies reviewed | 98 | Systematic review; snowballing and database search, published through 2022 |
| Studies reporting a concrete saving percentage | 27 of 98 | Self-reported by each primary study; no common definition imposed |
| Range of reported savings | 13% to 115% | Each figure uses its own baseline, workload, hardware and measurement boundary |
| Studies reporting ≥50% saving | 17 of 27 | Same caveat |
| Source of the 115% figure | Zhang, Davoodi and Hu (2018), structure simplification of trained deep neural networks | Single study; metric definition not given in the review |
| Studies using laboratory experiments | 73 of 98 | Research-strategy classification |
| Field experiments | 6 of 98 | " |
| Computer simulations | 5 of 98 | " |
| Position papers with no research strategy | 12 of 98 | " |
| Studies with academic authors only | 75 of 98 | Authorship classification |
| Academic and industrial mix | 20 of 98 | " |
| Industrial authors only | 3 of 98 | " |
| Studies targeting academic readers | 85 of 98 | Intended-readership classification |
| Studies targeting general public | 5 of 98 | " |

Water consumption is not a category in this review. The 98 studies are classified on energy and carbon.

## Methodology

Systematic literature review following established guidelines: database search plus snowballing, explicit inclusion and exclusion criteria, then classification of each primary study along axes including topic, AI lifecycle phase, algorithm class, data type, research strategy, industry involvement, intended readership and reported energy saving. Energy-saving percentages are extracted as each primary study reports them; the review performs no re-measurement, no normalisation and no meta-analysis of effect size.

## Limitations and conflicts

No funding statement and no conflicts declared; all three authors are academic. The review's own limitations apply to the saving figures: extraction is from what each paper states, with no verification of the measurement instrument, the baseline configuration or the workload. Savings drawn from pruning and quantisation studies typically measure inference energy on a single model and device, and generalise poorly to fleet-level consumption. The coverage ends in 2022, so it predates the transformer-scale inference workloads that dominate current AI energy questions. The 115% figure could not be traced to a stated definition in the accessible version of the primary study (the openly available artefact for Zhang et al. 2018 is the conference slide deck, which does not contain the figure; the IEEE journal article is paywalled).

## Relation to existing corpus

No direct overlap with the water-footprint sources in this folder. The review establishes that efficiency savings quoted in the Green AI literature carry no common boundary, which is the same defect that `research/water/017-google-2025-gemini-water-measurements.md` identifies in per-prompt energy estimates and that `research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md` quantifies for per-prompt water.

---
Retrieved: 2026-09-19
Search: OpenAlex for DOI 10.1002/widm.1507; full text via arXiv 2301.11047 PDF (Wiley 403s automated requests)
