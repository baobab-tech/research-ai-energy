# IEA baseline: data centres used 415 TWh in 2024 (1.5% of global electricity), projected to ~945 TWh by 2030

**Topic:** GHG emissions — authoritative aggregate electricity figures and scenario ranges
**Source:** International Energy Agency, *Energy and AI*, 2025
**Type:** agency report
**URL:** https://www.iea.org/reports/energy-and-ai/energy-demand-from-ai
**Published:** 2025-04

## Finding

The IEA's *Energy and AI* is the reference dataset nearly every downstream AI emissions estimate is built on, including de Vries-Gao (022) and Guidi et al. (030). It puts global data-centre electricity at about 415 TWh in 2024, roughly 1.5% of global electricity consumption, growing 12% annually over the prior five years. The Base Case reaches about 945 TWh by 2030 — just under 3% of global electricity. Critically, the IEA does **not** report an AI-specific figure directly; it attributes AI through the "accelerated servers" category, which is a hardware proxy, not a workload measurement.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Global data-centre electricity, 2024 | ~415 TWh (1.5% of global) | All data centres, facility-level incl. cooling |
| Growth, 2019-2024 | 12%/yr | |
| Base Case, 2030 | ~945 TWh (<3% of global) | ~15% CAGR 2024-2030 |
| Accelerated-server growth, Base Case | 30%/yr | vs 9%/yr conventional servers |
| AI attribution mechanism | Accelerated servers = ~half of net increase to 2030 | Hardware proxy, not workload metering |
| Lift-Off Case, 2035 | ~1,700 TWh (4.4% of global demand) | High AI adoption |
| High Efficiency Case, 2035 | ~970 TWh (2.6%) | Aggressive efficiency |
| Headwinds Case, 2035 | ~700 TWh (<2%) | Supply-chain/grid constraints |
| US increase to 2030 | +~240 TWh (+130%) | |
| China increase to 2030 | +~175 TWh (+170%) | |
| US + China share of growth to 2030 | ~80% | |

## Methodology

Bottom-up build from server installed base, split between conventional and accelerated (GPU/TPU/ASIC) servers, multiplied by utilisation and PUE assumptions, aggregated regionally. Inputs come substantially from proprietary market-research datasets (IDC, Omdia, SemiAnalysis) that are not publicly auditable. The four 2035 cases are scenarios, not forecasts with probabilities attached; the spread of 700-1,700 TWh is a factor of 2.4 and reflects genuine structural uncertainty about AI adoption, chip supply and grid interconnection, not measurement error.

## Limitations and conflicts

The IEA is an intergovernmental body funded by member states and has no commercial stake, but its inputs are purchased from vendors serving the data-centre industry. The report does not disaggregate AI from other accelerated workloads (scientific computing, rendering, crypto), so "AI share" is inferred. The page cited gives no CO2 figures for data centres — emissions must be derived by applying a grid intensity, which is where most downstream error enters. Facility-level PUE is modelled, not metered.

## Relation to existing corpus

Fills the largest gap flagged in the corpus. Before this file the IEA appeared nowhere in `research/` except as a line in `research/_log.md` recording a search that returned "general papers." Supersedes nothing; it is the baseline that 022, 029 and 030 all build on or benchmark against.

---
Retrieved: 2026-09-19
Search: WebFetch iea.org/reports/energy-and-ai/energy-demand-from-ai
