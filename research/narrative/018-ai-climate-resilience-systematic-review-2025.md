# Of 385 AI-for-climate-resilience studies, 64.4% address adaptation and 16% mitigation, from the same denominator, under a search string that requires a resilience term

**Topic:** narrative — what the AI-for-climate literature actually works on
**Source:** Rym Ayadi (Bayes Business School, City University London; Euro-Mediterranean Economists Association), Yeganeh Forouheshfar (EMEA), Omid Moghadas (Université de Reims Champagne-Ardenne), 2025
**Type:** peer-reviewed (systematic literature review)
**URL:** https://doi.org/10.3389/fclim.2025.1585331
**Published:** 2025-08

## Finding

A PRISMA review of 385 peer-reviewed studies classifies each one as addressing climate adaptation, mitigation, or both, mutually exclusively and against the same denominator: 64.4% adaptation, 19.4% both, 16% mitigation. The three shares sum to 99.8%, so the roughly four-to-one ratio of adaptation to mitigation-only work is a like-for-like comparison, and the authors report a two-sample test of proportions across the three categories at p < 0.0001. The result has to be read against the search protocol that produced it: the query requires a resilience term (Resilience, System Robustness, System Adaptability, Vulnerability Reduction, Robust Systems) alongside the AI and climate terms, which selects for adaptation framing before any study is classified. Sectorally the corpus concentrates on agriculture, forestry and food (30.39%) and cities and infrastructure (25.45%), while energy and industry takes 11.95%, so the sectors that emit most are not where this literature is.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Records identified | 1,612 | Dimensions.ai 680, Scopus 485, Web of Science 447 |
| Unique records after deduplication | 926 | — |
| Excluded at title and abstract screening | 272 | thematic relevance |
| Full texts assessed | 654 | — |
| Studies included | 385 | peer-reviewed, English, 1 January 2000 to 4 February 2025 |
| Adaptation only | 64.4% | of 385, coded classification |
| Both adaptation and mitigation | 19.4% | of 385, same denominator |
| Mitigation only | 16% | of 385, same denominator |
| Classical machine learning / general ML | 51.43% (198 studies) | of 385, method classification |
| Deep learning / neural networks | 22.34% (86 studies) | of 385 |
| Traditional ML and ensemble models | 8.3% | of 385 |
| Agriculture, forestry and food | 30.39% (117) | of 385, sector classification |
| Cities and infrastructure | 25.45% (98) | of 385 |
| Coastal and marine | 11.95% (46) | of 385 |
| Energy and industry | 11.95% (46) | of 385 |
| Water resources | 8.05% (31) | of 385 |
| Health | 0.52% (2) | of 385 |
| Global-scale studies | 34.3% | of 385, regional classification |
| Asia | 31.9% | of 385 |
| Europe | 11.7% | of 385 |
| North America | 10.4% | of 385 |
| Africa | 7.5% | of 385 |
| Oceania | 2.3% | of 385 |
| South America | 1.8% | of 385 |
| Published in 2024 | 51.69% (199) | of 385 |
| Published in 2023 | 18.18% (70) | of 385 |
| Published in 2025 up to 4 February | 10.65% (41) | of 385 |

## Methodology

Search string in three conjunctive blocks: AI terms (Artificial Intelligence, AI, Machine Learning, Deep Learning, Neural Networks, LLM, Large Language Model) AND resilience terms (Resilience, System Robustness, System Adaptability, Vulnerability Reduction, Robust Systems) AND climate terms (Climate Change, Global Warming, Climate Variability, Climate Crisis, Climate Adaptation, Climate Mitigation, Climate Resilience). Three databases, peer-reviewed English articles only; Google Scholar was excluded to avoid non-peer-reviewed material. Screening ran through the CADIMA tool, with the two authors double-screening a subset to align criteria. Inclusion required an explicit AI application to system-level resilience and a reported measurable outcome; 11 studies were excluded for lacking a measurable outcome, 4.3% of full-text exclusions. Classification into adaptation, mitigation or both is the authors' coding of each paper's stated focus. The review counts what studies are about. It measures no emissions, energy or avoided emissions, and it does not assess whether any classified application achieved its claimed outcome.

## Limitations and conflicts

The authors declare no financial support and no commercial or financial relationship. ChatGPT was used for English editing and NotebookLM for summarising referenced papers, which the authors disclose; a summarisation tool applied inside a classification exercise introduces an unquantified coding-error channel.

The middle block of the search string is the binding constraint on the headline result. A query that requires a resilience, robustness, adaptability or vulnerability term will under-return mitigation work, which is usually framed as decarbonisation, emissions reduction or energy transition rather than resilience, so the 64.4-to-16 split measures the composition of resilience-framed literature, not of AI-for-climate literature. The authors restrict themselves to system-level resilience by design and list the exclusion of micro-level work as a limitation. Coverage is English-only and confined to three databases. The corpus is heavily recent, with 51.69% published in 2024 alone, so the classification largely describes a two-year window. Inclusion required a "measurable outcome" as reported by each study, with no verification that the outcome was measured in deployment rather than simulation.

## Relation to existing corpus

Confirms at the level of research topic what `narrative/028-carmeno-2026-systematic-review-83-percent-positive.md` finds at the level of reported valence across a larger corpus of 1,291 studies: the AI-and-environment literature is narrow in what it examines. The 11.95% share for energy and industry here is consistent with that review's finding that assessments concentrate on application-level effects. The under-population of mitigation work bears on the adoption-rate silence in `narrative/021-iea-2025-energy-and-ai-avoided-emissions-scenario.md`, whose 1,400 Mt scenario rests on mechanisms the IEA itself says have no momentum toward widespread adoption.

---
Retrieved: 2026-09-19
Search: DOI 10.3389/fclim.2025.1585331; Frontiers open-access PDF extracted locally
