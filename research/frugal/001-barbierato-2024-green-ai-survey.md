# Survey of 48 Green AI papers, clustered by k-means, concluding that accuracy may have to fall

**Topic:** Frugal AI - efficiency techniques and the state of the Green AI literature
**Source:** Barbierato & Gatti (Catholic University of the Sacred Heart, Brescia), 2024
**Type:** peer-reviewed
**URL:** https://doi.org/10.1109/access.2024.3360705
**Published:** 2024-01

## Finding

The survey organises 48 manually selected papers into three clusters and describes the Green AI techniques they propose. The Red AI and Green AI terms are attributed in the text to Schwartz et al., and the properties the survey ascribes to them (accuracy saturating as hardware grows, computational cost rising exponentially, performance scaling at best logarithmically with model complexity, diminishing returns over time) are reported as Schwartz et al.'s results. The abstract's conclusion that "it will be necessary to decrease the level of accuracy of production systems" unless training and inference procedures reduce their impact is the authors' inference from the surveyed literature. No experiment, benchmark or model run in this paper tests an accuracy-against-energy trade-off.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Papers surveyed | 48 | Manually downloaded, selected against three inclusion criteria |
| Clusters | 3 | TF-IDF vectorisation of full text plus k-means; labelled carbon footprint/sustainability/Green AI, BERT-GPT-GAN models, training optimisation |
| Sub-clusters within cluster 1 | 4, first containing 7 papers | Second k-means pass within cluster 1 |
| Energy and carbon figures for BERT, GPT, GAN and PaLM | reproduced from the originating studies | Stated inclusion criterion; the survey quotes hardware where the original gives it |

The survey reports no measurement of its own. Every energy or carbon number in it carries the boundary of the paper it was taken from.

## Methodology

Literature selection by the two authors against three criteria: papers introducing the Green AI problem, papers giving quantitative energy measures for training and inference of notable large models, and papers proposing training optimisations. Full text of each retained article was TF-IDF vectorised and clustered with k-means into three clusters, then cluster 1 and cluster 2 were each re-clustered. Cluster count is asserted, not selected by a stated criterion; the paper says comparison of clustering models is out of scope. The survey narrates each cluster and describes techniques including quantization, binarisation, pruning, structured transforms, transfer learning and batch-size scaling, with the trade-offs reported by their original authors.

## Limitations and conflicts

Both authors are at a single Italian university department. IEEE Access is author-funded open access; no external funding or conflict is declared and none is apparent. The article is a secondary source throughout. Selection was manual with no search string, database or date window given, so the corpus cannot be reproduced. The concluding trade-off claim rests on Schwartz et al.'s scaling observations rather than on evidence assembled here, and the paper's own stated limitation is that it does not cover policy instruments for shifting practice from Red AI to Green AI. Hardware manufacturing and embodied emissions are not treated.

## Relation to existing corpus

Provides a route into the primary efficiency literature that the frugal folder covers. It contradicts nothing and confirms nothing, since it measures nothing.

---
Retrieved: 2026-09-19
Search: OpenAlex DOI lookup, then the Università Cattolica institutional copy of the IEEE version of record
