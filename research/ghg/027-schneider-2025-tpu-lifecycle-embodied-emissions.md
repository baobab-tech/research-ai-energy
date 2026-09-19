# First published manufacturing emissions for an AI accelerator: 386-692 kgCO2e embodied per TPU chip over six years; operational still dominates at 70-90%

**Topic:** GHG emissions — embodied/manufacturing emissions of AI accelerators
**Source:** Ian Schneider, Hui Xu, Stephan Benecke, David Patterson, Keguo Huang, Parthasarathy Ranganathan, Cooper Elsworth — Google, 2025
**Type:** preprint (first-party corporate LCA)
**URL:** https://arxiv.org/abs/2502.01671
**Published:** 2025-02-01

## Finding

Google published per-chip cradle-to-grave emissions for five TPU generations — the first disclosure of manufacturing emissions for any AI accelerator. Embodied emissions (manufacturing, transport, data-centre construction, end-of-life) run 386-692 kgCO2e per chip over a six-year life, against operational emissions of 1,154-2,141 kgCO2e market-based or 3,104-5,759 kgCO2e location-based. Operational therefore dominates at 70-90% of lifetime emissions, with manufacturing under 25% and data-centre construction under 5%. Memory drives the embodied trend: HBM plus host DRAM is roughly 38% of manufacturing CO2e, and the v6e host carries 1,536 GiB DRAM against v5e's 512 GiB.

## Key Data

| Metric | TPU v4i (2020) | TPU v5e (2023) | TPU v6e (2024) | Boundary / method |
|--------|-----|-----|-----|-----|
| Embodied CO2e per chip | 386 kg | 402 kg | 692 kg | 6-year life, machine emissions normalised per chip |
| — data-centre construction | 59 kg | 59 kg | 109 kg | |
| — CPU manufacturing + transport | 119 kg | 106 kg | 260 kg | |
| — TPU manufacturing + transport | 208 kg | 238 kg | 323 kg | |
| Operational CO2e (market-based / location-based) | 1,166 / 3,137 kg | 1,154 / 3,104 kg | 2,141 / 5,759 kg | Measured fleet power x PUE 1.10 |
| Embodied CCI | 114 | 103 | 38 | gCO2e per 10^18 FLOPs |
| Operational CCI (MB / LB) | 346 / 929 | 295 / 793 | 118 / 316 | gCO2e per 10^18 FLOPs |
| Mean measured power | 1,184 W/machine | 1,171 W | 2,173 W | Fleet measurement, not TDP |

| Other | Value |
|---|---|
| Machine manufacturing emissions, v4i -> v6e | +1.8x, while peak performance +4.7x |
| Embodied CCI, v5e -> v6e | -66% |
| Total CCI, v4i -> v6e | 3x improvement |
| v5p vs v4 manufacturing | +55% (TPU component +80%; HBM +95%, ASIC +70%) |
| TPU manufacturing+transport range across all five | 208-585 kg/chip |
| Prior literature placeholder for a GPU | 150 kg — Google's TPU figures are 1.5-4x larger |
| Google average data-centre PUE applied | 1.10 |
| Worked example: GPT-3 training (3.14 x 10^23 FLOPs) | ~107 tCO2e on TPU v4; ~89 t on v5p |

## Methodology

ISO-compliant cradle-to-gate LCA at machine level using proprietary chip parameters (technology node, die size, yield), combined with operational emissions from fleet-measured power at five-minute per-chip granularity multiplied by Google's average PUE of 1.10. The authors emphasise that measured power is 2-3x lower than thermal design power, so studies using TDP overstate operational energy substantially. The CCI metric (gCO2e per 10^18 FLOPs) is introduced to make embodied and operational carbon commensurable. Utilised FLOPs come from internal instrumentation, not from peak specifications.

## Limitations and conflicts

Google authored, measured, and self-verified this; none of the underlying chip parameters, supplier emission factors or fleet telemetry are independently auditable, and the results support Google's position that its hardware is improving on carbon efficiency. Several die-size and HBM-type fields in Table 1 are redacted as "N.A." for competitive reasons, so the manufacturing figures cannot be reconstructed. The paper is candid that accounting choice moves the answer: operational emissions are 2.7x higher under location-based than market-based accounting, and the embodied share of lifetime emissions swings from ~24% (market-based) to ~11% (location-based) for v6e purely by that choice. TPUs are not GPUs — NVIDIA has published nothing equivalent, so these numbers cannot be assumed to transfer. Excludes network fabric beyond the machine and any supply-chain emissions Google's suppliers do not report.

## Relation to existing corpus

Closes the gap the GHG index explicitly flags: "No specific GPU/chip manufacturing emissions data in 2024-2025 literature." Qualifies `research/ghg/020-rozycki-2025-energy-aware-ml-models-review.md`, which reports that embodied emissions "often eclipse operational" — on Google's own first-party data for AI accelerators they do not, at 10-25% of lifetime total. Extends `research/ghg/015-tpu-v4-energy-efficiency-numbers.md` (Jouppi et al. 2023) from operational efficiency to full lifecycle.

---
Retrieved: 2026-09-19
Search: WebSearch "Google TPU life cycle assessment embodied emissions v4i v6e"; arXiv PDF 2502.01671 extracted locally
