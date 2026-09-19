# Eight-phase lifecycle framing for chatbots, with ChatGPT service electricity modelled at up to 7.128 TWh/year

**Topic:** GHG emissions - lifecycle framing and inference-phase electricity
**Source:** Jiang, Sonne, Li, You & You (Sichuan University; Aarhus University; Chinese Academy of Sciences; Cornell University; University of Glasgow), 2024
**Type:** peer-reviewed perspective
**URL:** https://doi.org/10.1016/j.eng.2024.04.002
**Published:** 2024-04

## Finding

The paper sets out eight lifecycle phases for LLM-powered chatbots and names hardware manufacturing and LLM training as the two expected to be most energy-intensive, with the chatbot service phase identified as an emerging hotspot. The eight phases are: chatbot R&D; hardware manufacturing including GPUs, TPUs, supercomputers and service devices; global commercial logistics; facility operations and maintenance; massive data collection and management centres; LLM training and fine-tuning; online and offline chatbot services; and hardware material recycling and waste disposal. Quantification is limited to a scenario grid for the service phase and to training figures reproduced from other studies. Under nine service scenarios built from queries per visit and per-query efficiency, five exceed the final training run of GPT-4 and eight exceed that of GPT-3 in monthly electricity.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Lifecycle phases identified | 8 | Conceptual, framed on IEC 62890:2020; not individually quantified |
| GPT-3 final training run | 1287 MWh, 552 tCO2-eq | Reproduced from Patterson et al.; final run only, excludes fine-tuning and updates |
| GPT-4 final training run | 7200 MWh, about 3088 tCO2-eq | Electricity from a TRG Datacenters trade report; emissions scaled by the authors using the GPT-3 intensity |
| Transformer with 213M parameters | about 300 tCO2-eq | Reproduced from Strubell et al.; training including neural architecture search |
| 5000 pretraining runs of GPT-3 scale | up to 2.76 MtCO2-eq | Authors' arithmetic on an assumed 5000 trial models; illustrative, not observed |
| ChatGPT service electricity, worst case | 23,364 MWh/month | Modelled scenario 3: 590M visits, 10 queries/visit, 0.00396 kWh/query |
| ChatGPT service electricity, worst case annualised | up to 7.128 TWh/year | Modelled; 1.5 billion visits/month peak, delivered via Google search |
| Per-query electricity assumptions | 0.00396 / 0.00297 / 0.00198 kWh | Low, medium and high efficiency; from a TRG Datacenters report |
| GPU shipments 2022, annual electricity | about 9500 GWh | Cited secondary figure; specialised GPUs shipped in 2022 |
| LLaMA GPU counts | 16 inference, 100+ fine-tuning, 2000 training (A100) | Cited secondary figure |

## Methodology

A perspective article in the Energy Systems Engineering section of Engineering. The lifecycle phases are derived conceptually from LCA practice and IEC 62890:2020, not from an inventory. The service-phase estimate is a nine-cell scenario grid crossing three queries-per-visit assumptions (1, 5, 10) with three per-query electricity assumptions, applied to Similarweb visit counts for chat.openai.com. Training figures are taken from Patterson et al. and Strubell et al. The GPT-4 electricity figure and all per-query intensities come from a single commercial data centre firm's blog report. The three proposed mitigation pathways are policy proposals, not modelled interventions.

## Limitations and conflicts

Peng Jiang was supported by the National Natural Science Foundation of China (72061127004, 72104164) and a Chinese research centre grant. The authors declare no conflict of interest. The paper quantifies none of its eight phases on its own data: hardware manufacturing and logistics, which it names as dominant, carry no number at all. Per-query electricity comes from a vendor blog rather than measurement, and the same source supplies the GPT-4 training electricity, so the service scenarios and the training comparator are not independent. The 2.76 MtCO2-eq figure rests on an assumed 5000 pretraining runs. Visit counts are used as a proxy for request volume, with queries per visit assumed. Water, embodied hardware emissions and grid location are outside the boundary.

## Relation to existing corpus

The claim that service-phase electricity can exceed the training run agrees in direction with Chien et al. in ghg/014, who model inference at 25 times the training emissions of GPT-3 for a ChatGPT-scale workload. The eight-phase boundary is wider than the LCA in ghg/006, which covers training, inference, web hosting, storage, networks and user terminals but excludes logistics and end-of-life.

---
Retrieved: 2026-09-19
Search: OpenAlex DOI lookup, then the University of Glasgow Enlighten copy of the open access version of record
