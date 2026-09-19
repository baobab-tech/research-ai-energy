# ChatGPT-scale inference modelled at 25x the training emissions of GPT-3, with carbon-aware routing cutting 35%

**Topic:** GHG emissions - inference workload modelling and carbon-aware request routing
**Source:** Chien, Lin, Nguyen, Rao, Sharma & Wijayawardana (University of Chicago; Argonne National Laboratory), 2023
**Type:** peer-reviewed workshop paper
**URL:** https://doi.org/10.1145/3604930.3605705
**Published:** 2023-07

## Finding

A workload model of a ChatGPT-like service at 11 million requests per hour gives 12.8 thousand tonnes CO2 per year, 25 times the emissions of training GPT-3 once. Routing requests to the region with the lowest hourly carbon intensity, which the authors call CarbonMin, cuts modelled emissions 35% against the same workload served locally, with no change in average request latency across output lengths. Under a 2035 scenario with 55 times the workload and grids three times less carbon-intense on average, CarbonMin cuts 56%; capacity is the binding constraint, and adding one times headroom raises the cut to 71%. The routing decisions use average carbon intensity, not marginal.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Modelled service emissions | 12.8 kt CO2/year at 11M requests/hour | Modelled; operational plus embodied GPU emissions, 8 regions |
| Inference to training ratio | 25x GPT-3 training, one year | Modelled; 55,966,667 vs 2,236,467 A100 GPU-hours per year |
| Same ratio for a search-scale workload | 1386x | Modelled; Google-RR workload variant |
| CarbonMin reduction, 2022 grids | 35% | Modelled against Local routing, capacity-constrained, normalised to the all-region average |
| CarbonMin reduction, unlimited capacity, 2022 | 63% | Modelled; capacity constraint removed |
| CarbonMin reduction, 2035 scenario | 56% | Modelled; 55x workload, 3x lower average grid carbon intensity |
| CarbonMin reduction, 2035 with 1x headroom | 71% | Modelled; 73x lower per-inference emissions |
| Net 2035 emissions versus 2022 | 1.2x, that is 20% higher, for 55x workload | Modelled; efficiency and routing do not hold emissions flat |
| Compute per request | 2.07 A100 GPU-seconds average | Derived: 0.35 TFLOPs/inference at GPT-3 scale in BF16, 5 inferences per output word, 185 output words, 156 TFLOPS at 50% efficiency |
| Embodied emissions per GPU | 318 kgCO2 | Estimated from Azure ND A100 v4 specifications, amortised over a 3-year lifetime |
| Carbon intensity source | hourly average carbon intensity (ACI) | RiPiT and Electricity Maps, 2022 hourly data |
| Regions modelled | 8 | California, Texas, Iowa, UK, Ireland, Germany, Japan, India |
| Demand geography | 39% USA, 35% Europe | From documented ChatGPT usage rates and national population, skewed for waking hours |

## Methodology

A workload model built from public ChatGPT usage figures, apportioned across eight exemplar cities by usage rate and population and skewed for waking hours. Per-request compute is derived analytically from GPT-3 parameter count, an assumed sampling window of five inferences per output word, a measured average of 185 output words per request, and A100 throughput at 50% efficiency. Operational emissions apply hourly average carbon intensity by region; embodied emissions amortise estimated per-instance manufacturing footprints over a three-year lifetime. Four routing policies are simulated over one year: Local, Balance, CarbonMin and CarbonMin with the capacity constraint removed. Latency is computed as compute time plus median measured round-trip latency between Azure region pairs, and quality of service is checked at 25, 100 and 300 output words.

## Limitations and conflicts

University of Chicago and Argonne National Laboratory; Electricity Maps provided data and is acknowledged. No commercial funding or conflict is declared. Every figure is modelled, none measured on a production service. Per-request compute is analytic and rests on an assumed five inferences per output word and 50% GPU efficiency; the true serving stack uses batching, KV caching and quantization that the model does not represent. Average carbon intensity attributes grid-average emissions to a marginal load, which overstates the benefit of shifting where the marginal generator is not the average one. Cooling, networking and non-GPU server power are outside the boundary, as is water. The 2035 scenario assumes 55x workload growth and 3x grid decarbonisation, both stipulated. Data-residency, latency-tier and regulatory limits on cross-border routing are not modelled beyond the capacity constraint. Seven pages, workshop-reviewed.

## Relation to existing corpus

The 25x inference-to-training ratio supports the direction of the service-phase argument in ghg/001, which reaches a comparable conclusion by a different route. The exploited spread in regional grid intensity matches the 0.071 to 0.992 tCO2/MWh range used in the Chinese siting model in datacenters/009.

---
Retrieved: 2026-09-19
Search: OpenAlex DOI lookup, then the HotCarbon 2023 proceedings PDF at hotcarbon.org
