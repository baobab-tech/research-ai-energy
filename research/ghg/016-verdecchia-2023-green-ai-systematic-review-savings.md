# Green AI savings across 98 studies: only 27 report a number at all, median 53%, and the often-quoted 115% is a single unexplained outlier

**Topic:** GHG emissions — how much energy Green AI techniques actually save
**Source:** Roberto Verdecchia (University of Florence), June Sallou and Luís Cruz (TU Delft), 2023
**Type:** peer-reviewed
**URL:** https://doi.org/10.1002/widm.1507 (open preprint: https://arxiv.org/abs/2301.11047)
**Published:** 2023-06

## Finding

The review transcribes whatever percentage each primary study reports and applies no common definition, normalisation or baseline. Of 98 primary studies, 71 report no saving figure. The 27 that do span 13% to 115% with a median of 53%, and 17 of them report at least 50%. The 115% maximum, which the abstract carries and which is widely requoted, comes from one 2018 paper on eliminating neurons from CaffeNet's fully-connected layers, where energy is produced by an analytical model rather than measured. No saving against a fixed baseline can exceed 100%, and every other value in the set is 97% or below, so 115% is an artifact of that study's own reporting convention and is not comparable with the rest.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Primary studies reviewed | 98 | 16 from automated search of Google Scholar, Scopus, Web of Science; 82 added by two rounds of bidirectional snowballing to saturation |
| Studies reporting any numeric energy saving | 27 of 98 | reviewers' extraction field, transcribed as the primary study reported it |
| Distribution of those 27 | min 13%, median 53%, max 115% | verified against the published extraction sheet |
| Studies reporting >=50% | 17 of 27 | among those reporting a number, i.e. 17 of 98 overall |
| Second-highest value | 97% | the 115% is the only value above 100% |
| Source of the 115% | Zhang, Davoodi & Hu, IEEE JETCAS 2018 | neuron elimination in a trained DNN; training phase, image data, laboratory validation, energy from an analytical model |
| Study types | 52 solution, 35 observational, 11-12 position | the figure and text disagree on the position-paper count |
| Publications per year | 1 (2015), 3, 6, 7, 7, 20, 33, 21 (2022) | growth concentrated from 2020 |
| Phase studied | training | the dominant focus; inference under-represented |
| Data type | image | the dominant data type |
| Research strategy | laboratory experiment | the dominant strategy; field experiments and simulations rare |
| Dataset sizes | 1k to 40M data points | ~half the studies use >=1M |
| Venue split | 47 conference, 39 journal, 12 workshop | |
| Tool availability | scarce | few studies ship a usable measurement tool |

## Methodology

A systematic literature review with a stated protocol: a conservative automated query across three indexing platforms yielding 16 seed studies, then recursive backward and forward snowballing until theoretical saturation at 98. Two researchers independently screened and extracted. Extraction fields include study type, topic, domain, data type, phase, dataset size, energy savings, industry involvement, intended reader and tool availability. Inclusion criterion I4 restricts the corpus to software-centric Green AI, which excludes hardware-specific work and therefore excludes accelerator and data-centre efficiency entirely. The extraction sheet and analysis scripts are published at https://github.com/luiscruz/slr-green-ai.

## Limitations and conflicts

Academic authors at two universities; no funding statement and no declared conflict. The savings figures are the weak point. The review never defines what a saving is measured against, and the extraction sheet records only a bare percentage per study, so the 13-115% range aggregates values computed against different baselines, on different workloads, at different phases, by different methods. Because only 27 of 98 studies report a number, and those are the studies with a result worth reporting, the distribution is subject to reporting bias and cannot be read as the expected saving from adopting Green AI. All the values are within-study technique-versus-baseline comparisons on laboratory workloads, mostly small image models; none is a system-level, fleet-level or production measurement, and none accounts for rebound. The corpus closes in 2022, so it predates the generative-AI scale-up.

## Relation to existing corpus

Duplicated as `research/water/021-verdecchia-2023-green-ai-systematic-review.md`, which covers the same paper. The finding that efficiency results are laboratory-scale and do not constrain totals is the argument of `research/frugal/026-wright-2025-compute-energy-carbon-efficiency.md`. The review's exclusion of hardware-specific work means it has no bearing on `research/ghg/015-tpu-v4-energy-efficiency-numbers.md` or `research/ghg/027-schneider-2025-tpu-lifecycle-embodied-emissions.md`.

---
Retrieved: 2026-09-19
Search: DOI 10.1002/widm.1507 via Crossref; arXiv 2301.11047 PDF and the GitHub replication package extraction sheet, both extracted locally
