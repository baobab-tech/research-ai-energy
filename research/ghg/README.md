# GHG Emissions

30 excerpts on the greenhouse-gas footprint of AI: training, inference, embodied emissions, and
the aggregate figures published by agencies and operators.

[Full index](_index.md)

## Established figures

| Quantity | Value | Boundary | Source |
|---|---|---|---|
| Global data-centre electricity, 2024 | 415 TWh, 1.5% of global | all data centres; AI not separable | [023](023-iea-2025-energy-and-ai-datacentre-electricity.md) |
| Global data-centre electricity, 2030 | ~945 TWh | IEA base case | [024](024-iea-2026-key-questions-energy-ai.md) |
| US data-centre electricity, 2024 | 192 TWh, 4.7% of national | LBNL | [datacenters/016](../datacenters/016-lbnl-2026-us-dc-energy-2025-update.md) |
| AI emissions, 2025 | 32.6 to 79.7 MtCO2 | operational only; excludes manufacturing | [022](022-de-vries-gao-2025-ai-carbon-water-footprint.md) |
| Per-query energy | 0.31 Wh median, IQR 0.16 to 0.60 | full-node, PUE-inclusive, 8xH100 FP8 | [026](026-oviedo-2026-per-query-inference-energy.md) |
| Per-question energy, measured | 0.058 to 4.26 Wh | device counters only; no PUE, cooling or network | [019](019-dauner-2025-energy-costs-communicating-ai.md) |
| Embodied per TPU chip | 386 to 692 kgCO2e | manufacturing, six-year life; operational is 70-90% of lifetime | [027](027-schneider-2025-tpu-lifecycle-embodied-emissions.md) |
| Hyperscale carbon intensity | 545 gCO2/kWh, 48% above US grid | 403 sites attributed to eGRID plants | [030](030-guidi-2026-us-hyperscale-carbon-intensity.md) |

## Reading these numbers

**No operator discloses AI-specific emissions.** Every AI figure here is inferred from total
data-centre load using an assumed AI share. The 2025 estimate is a model built on the IEA's
model, which rests on proprietary datasets that cannot be independently audited. Its floor is
2.4x below its ceiling; the upper bound is often quoted alone.

**Corporate totals depend on the Scope 2 method.** Google reports 14.5 MtCO2e for 2025 while its
location-based Scope 2 alone is 15.1 Mt ([028](028-google-2026-environmental-report-accounting-gap.md)).
Microsoft's FY25 total of 21.1 Mt rose 26%, mostly from dropping non-additional certificates
([029](029-microsoft-2026-sustainability-report-fy25.md)). Company comparison is in
[`/research/washing/`](../washing/).

**Efficiency ratios usually carry an electricity-accounting term.** The TPU v4 figure of 18.3x
lower CO2e decomposes as 2.85x energy times a 6.4x electricity-factor ratio: Google's
market-based Oklahoma factor of 0.074 kgCO2e/kWh against the IEA global average of 0.475 charged
to a hypothetical comparator ([015](015-tpu-v4-energy-efficiency-numbers.md)). The electricity
factor contributes more than hardware and PUE combined.

**Training figures disagree by 2x on undisclosed runs.** Grok 4 is estimated at 72,000 tCO2e by
the Stanford AI Index and ~154,000 tCO2e by Epoch ([032](032-epoch-2026-grok4-training-emissions.md)).

## Comparisons that need their counterfactual read

The claim that AI emits 130 to 1,500x less CO2e per page than a human
([013](013-tomlinson-2024-ai-vs-human-emissions-comparison.md)) charges the human writer a
pro-rata share of their entire national per-capita annual footprint, divided across all 8,760
hours of the year. The writer emits the same whether writing or not, so no counterfactual is
established. On the AI side, 84% of the 2.2 gCO2e attributed to ChatGPT is amortised training
under an assumption that GPT-3 is fully retrained every month, and the inference term derives
from an informal blog estimate. The paper's own inputs yield ratios of 82x to 875x; the reported
130x to 1,500x are about 1.6x larger.

Reported efficiency savings are not normalised. The Green AI review's range of 13% to 115%
([016](016-verdecchia-2023-green-ai-systematic-review-savings.md)) covers 27 of 98 studies, each
self-reported against its own baseline with no common definition; the median is 53% and the 115%
is a lone outlier from one analytically-modelled pruning study. The review is restricted to
software-centric work and reports nothing on water.

## Embodied against operational

Two findings sit at different boundaries and do not conflict. Google's first-party TPU lifecycle
data puts operational at 70-90% of a chip's lifetime emissions
([027](027-schneider-2025-tpu-lifecycle-embodied-emissions.md)). The claim that embodied
emissions exceed operational ([020](020-rozycki-2025-energy-aware-ml-models-review.md)) inherits
a figure comparing manufacturing of **all computing equipment** worldwide, including 1.7 billion
phones, against ML training alone. Only the first bears on datacentre accelerators.

## Gaps

- Foundry-level emission factors per wafer. No primary TSMC or Samsung disclosure at that granularity.
- NVIDIA accelerator lifecycle assessment. No equivalent to Google's TPU LCA exists.
- Marginal emissions of added data-centre load. Attribution here is average-intensity only.
- Agentic and multi-turn workloads. Per-query measurements exclude tool calling by construction.
