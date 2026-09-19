# 55 green AI initiatives catalogued from vendor websites and practitioner blogs; the authors state that most still need empirical evaluation

**Topic:** narrative — what evidence stands behind the tools promoted as making AI green
**Source:** Yehia Ibrahim Alzoubi (American University of the Middle East, Kuwait) and Alok Mishra (Norwegian University of Science and Technology), 2024
**Type:** peer-reviewed (hybrid literature and grey-source review)
**URL:** https://doi.org/10.1016/j.jclepro.2024.143090
**Published:** 2024-08

## Finding

Fifty-five initiatives presented as reducing AI's environmental impact are catalogued in six categories: cloud optimization, model efficiency, carbon footprinting, sustainability-focused AI development, open-source initiatives, and green AI research and community. The authors state that their conclusions rest mainly on data gathered from the initiatives' own websites, professional websites, blogs and agencies, because the academic literature on these tools was too thin to review. The efficiency figures reported for individual tools are therefore the vendors' own: up to 50% power reduction for the NVIDIA green GPU platform, cited to NVIDIA, and up to 40% carbon footprint reduction for the Google AI platform, cited to Google Cloud. The authors close by calling for empirical evaluation of most of the tools they list, on the grounds that the tools are early-stage, and name eco2AI, Zeus and Aeva as still developmental.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Initiatives catalogued | 55 | authors' count; identified from academic databases plus vendor websites, practitioner blogs and professional publications, with no stated screening protocol or record counts |
| Categories | 6 | cloud optimization, model efficiency, carbon footprinting, sustainability-focused AI development, open-source initiatives, green AI research and community |
| NVIDIA green GPU platform power reduction | up to 50% | vendor claim, cited to NVIDIA; benchmark of optimized against traditional workloads on A100 GPUs; no independent verification |
| Google AI platform carbon footprint reduction | up to 40% | vendor claim, cited to Google Cloud; "specific optimization cases using TensorFlow Profiler and other platform features"; no boundary, baseline or sample stated |
| Mobile carriers expecting AI to cut network power use 10-15% | 30% of carriers | survey expectation reported via Statista; a belief, not a measurement |
| Tools named as still developmental | eco2AI, Zeus, Aeva | authors' assessment |

Background figures the paper reproduces from third parties, none of them its own measurement: GPT-3 training at 1,287 MWh and 552 tCO2e; 700,000 litres of fresh water for GPT-3 training; NVIDIA AI servers projected at about 85.4 TWh per year by 2027; worldwide AI spending of 154 billion USD in 2023.

## Methodology

A structured search of Elsevier, Wiley, Springer, Emerald, IEEE, Taylor, MDPI and Google Scholar on "(green AI OR green artificial intelligence) AND (energy OR power OR sustainability OR eco-friendly)", then an explicit widening to industry websites, practitioner blogs and professional publications after the academic yield proved small. No record counts, screening stages, inclusion criteria or PRISMA flow are reported, so the 55 is a convenience catalogue rather than a census, and the denominator of initiatives that exist is unknown. Each entry is written up as a prose summary of strengths, limitations and applications drawn from the source's own material. The paper performs no test, benchmark or reanalysis of any tool.

## Limitations and conflicts

The authors declare no competing financial interests. No funding statement appears. Neither author is affiliated with a vendor named in the catalogue.

The reliance on vendor material is stated by the authors, not inferred, and it determines what the numbers mean: a claim reproduced from a supplier's marketing page carries that supplier's unstated boundary and baseline. The "up to" construction on both headline percentages marks a best case, not a central estimate. The authors' own limitations section asks future work to validate the paper's discussions and to evaluate most of the listed tools empirically, which is a statement that the catalogue is not itself evidence that the tools work. The paper's carbon-footprinting section separately identifies the failure modes of the measurement tools it catalogues: variation in system boundaries, omission of upstream manufacturing and downstream disposal, and gaps on cooling and embodied hardware emissions.

## Relation to existing corpus

The catalogue's reliance on vendor-stated efficiency percentages is the pattern `narrative/024-google-2026-frozen-2008-pue-baseline-and-deepmind-claim.md` documents in detail for the DeepMind 40% cooling claim, which was never independently verified and which Google's 2026 report does not restate. The authors' finding that most green AI tools await empirical evaluation is the tool-level counterpart to the study-level result in `narrative/028-carmeno-2026-systematic-review-83-percent-positive.md`, where 83% of environmental studies portray AI's impact as positive and 11% consider systemic effects. The same source is written up from a different angle in `narrative/010-alzoubi-2024-green-ai-initiatives-validation-gap.md`.

---
Retrieved: 2026-09-19
Search: DOI 10.1016/j.jclepro.2024.143090; ScienceDirect blocked, full text obtained from the AMULET project repository copy and extracted locally
