# A narrative review whose claim that embodied emissions "eclipse" operational rests on a single cross-boundary comparison: all IT equipment manufactured worldwide versus ML training alone

**Topic:** GHG emissions — efficiency techniques, and the provenance of the embodied-versus-operational claim
**Source:** Rafał Różycki, Dorota Agnieszka Solarska, Grzegorz Waligóra — Poznan University of Technology, 2025
**Type:** peer-reviewed (MDPI *Energies*)
**URL:** https://doi.org/10.3390/en18112810
**Published:** 2025-05

## Finding

The review surveys model compression, pruning, quantization and hardware choice as levers on ML energy, and closes on a call for a dual strategy addressing both operational efficiency and the carbon intensity of hardware manufacturing. Its distinguishing claim, carried in the abstract and repeated three times in the conclusions, is that manufacturing emissions "in many cases eclipse those from operational activities". Traced to its single supporting citation, the claim is a restatement of Patterson et al. (CACM 2024), who compare the embodied carbon of every computing device manufactured worldwide in 2021 (1.7 billion phones, 340 million PCs, 12 million servers) against the operational carbon of ML training alone. The review restates this as a fact about ML hardware specifically, which the source does not establish. No original measurement supports it.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Stated embodied-to-operational ratio | "over 70 times greater" | quoted from the review; embodied CO2e of global IT equipment production in 2021 versus operational CO2e of ML training. Not a like-for-like comparison of one hardware class |
| Underlying source | Patterson et al., CACM 67(2), 2024 | scope: 1.7 bn cell phones, 340 M PCs, 12 M servers manufactured in 2021, against ML training operations |
| Techniques surveyed | model compression, pruning, quantization, hardware design, hyperparameter and AutoML optimisation | narrative survey; no pooled effect size |
| Primary studies included | not stated | no search protocol, inclusion criteria, screening record or study count is given |
| Original measurements | none | all figures are secondary citations |

No further number in this paper can be attached to a system boundary, so none is tabulated.

## Methodology

A narrative literature review. The paper states six objectives but no search strategy, no databases queried, no inclusion or exclusion criteria, no screening procedure, no PRISMA flow and no count of studies reviewed. Sections summarise cited work topic by topic. The embodied-emissions claim appears in the abstract, in section 4.1, and twice in the conclusions, each time with the same single citation and no derivation.

## Limitations and conflicts

Funded by Poznan University of Technology (project 0311/SBAD/0746); no commercial conflict declared, and none apparent. Published in *Energies*, an MDPI journal.

The central claim misstates its source. Patterson et al. compare a whole-sector manufacturing total, dominated by consumer phones, against a narrow operational slice; the review converts this into "the embodied emissions from the manufacturing of ML hardware often exceed the operational emissions", substituting one hardware class for all of them and one workload for all operations. The review also cites Wu et al. (2022) as support, but that paper says embodied carbon "can be even more consequential", not that it exceeds operational for AI accelerators. The absence of a review protocol means the selection of cited work cannot be audited and the survey cannot be reproduced.

## Relation to existing corpus

The embodied claim does not contradict `research/ghg/027-schneider-2025-tpu-lifecycle-embodied-emissions.md` so much as measure a different thing. Schneider et al. compare embodied and operational emissions of the same TPU chip over the same six-year life and find operational dominant at 70-90%, with embodied at 386-692 kgCO2e per chip against 1,154-2,141 kgCO2e operational market-based. That is the like-for-like accelerator comparison this review does not make. On datacentre AI accelerators the first-party lifecycle data therefore points the opposite way, while this review's inherited figure describes the global device manufacturing stock, where short-lived consumer hardware with low duty cycles genuinely does carry a high embodied share. Both can hold at once; only the narrower one bears on data-centre AI. `research/ghg/007-istrate-2024-digital-content-environmental-sustainability.md` covers the same lifecycle framing.

---
Retrieved: 2026-09-19
Search: DOI 10.3390/en18112810; PDF from mdpi-res.com extracted locally; citation [57] traced to Patterson et al., CACM 2024, and its scope confirmed from the author's own SLAC presentation slides
