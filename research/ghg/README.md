# GHG Emissions

32 excerpts on the greenhouse-gas footprint of AI: training runs, inference at scale, embodied
emissions in hardware, and the aggregate figures published by agencies and operators.

[Full index](_index.md)

## Established figures

| Quantity | Value | Boundary | Source |
|---|---|---|---|
| Global data-centre electricity, 2024 | 415 TWh, 1.5% of global | all data centres, AI not separable | [023](023-iea-2025-energy-and-ai-datacentre-electricity.md) |
| Global data-centre electricity, 2030 | ~945 TWh | IEA base case | [024](024-iea-2026-key-questions-energy-ai.md) |
| US data-centre electricity, 2024 | 192 TWh, 4.7% of national | LBNL 2026 update | [datacenters/016](../datacenters/016-lbnl-2026-us-dc-energy-2025-update.md) |
| AI emissions, 2025 | 32.6 to 79.7 MtCO2 | operational only, excludes manufacturing | [022](022-de-vries-gao-2025-ai-carbon-water-footprint.md) |
| Per-query energy | 0.31 Wh median, IQR 0.16 to 0.60 | full-node, PUE-inclusive, 8xH100 FP8 | [026](026-oviedo-2026-per-query-inference-energy.md) |
| Embodied per TPU chip | 386 to 692 kgCO2e | manufacturing, 6-year life | [027](027-schneider-2025-tpu-lifecycle-embodied-emissions.md) |
| Hyperscale carbon intensity | 545 gCO2/kWh, 48% above US grid | 403 sites attributed to eGRID plants | [030](030-guidi-2026-us-hyperscale-carbon-intensity.md) |

## Reading these numbers

**No operator discloses AI-specific emissions.** Every AI figure in this folder is inferred from
total data-centre load using an assumed AI share. The de Vries-Gao estimate is a model built on
the IEA's model, which rests on proprietary datasets from IDC, Omdia and SemiAnalysis that cannot
be independently audited.

**The 80 Mt figure in wide circulation is the ceiling of a range.** Its floor is 32.6 Mt, 2.4x
lower. See [022](022-de-vries-gao-2025-ai-carbon-water-footprint.md).

**Corporate totals depend on the Scope 2 method chosen.** Google reports 14.5 MtCO2e for 2025
while its location-based Scope 2 alone is 15.1 Mt ([028](028-google-2026-environmental-report-accounting-gap.md)).
Microsoft's FY25 total of 21.1 Mt rose 26%, mostly from dropping non-additional certificates
([029](029-microsoft-2026-sustainability-report-fy25.md)). The company-by-company comparison sits
in [`/research/washing/`](../washing/).

**Training figures disagree by 2x on undisclosed runs.** Grok 4 is estimated at 72,000 tCO2e by
the Stanford AI Index and ~154,000 tCO2e by Epoch ([032](032-epoch-2026-grok4-training-emissions.md)).

## Corrections held in this folder

[020](020-rozycki-2025-energy-aware-ml-models-review.md) states that embodied emissions often
eclipse operational. Google's first-party TPU lifecycle data puts operational at 70 to 90% of
lifetime emissions ([027](027-schneider-2025-tpu-lifecycle-embodied-emissions.md)). The
first-party measurement supersedes the review on this point for accelerators.

[018](018-wright-2025-efficiency-not-enough.md) was written from the abstract and misstates the
paper's thesis. A corrected excerpt from the full text is at
[frugal/026](../frugal/026-wright-2025-efficiency-not-enough-corrected.md).

## Gaps

- Foundry-level emission factors per wafer. No primary TSMC or Samsung disclosure at that granularity.
- NVIDIA accelerator lifecycle assessment. No equivalent to Google's TPU LCA has been published.
- Marginal emissions of added data-centre load. Attribution in this folder is average-intensity only.
- Agentic and multi-turn workloads. Per-query measurements exclude tool calling by construction.
