# Across 472 US Hyperscale Facilities, Electricity-Related Water Is 75% of Operational Water Consumption — and Lands in Different Places from Cooling Water

**Topic:** Water — facility-resolved scope 1 vs scope 2 water; siting relative to basin water stress
**Source:** Guidi and Dominici, Harvard University (Harvard T.H. Chan School of Public Health), 2026
**Type:** preprint (arXiv, cs.CY)
**URL:** https://arxiv.org/abs/2607.02531
**PDF:** https://arxiv.org/pdf/2607.02531
**Published:** 2026-06-05

## Finding

Mapping both water pathways separately for 472 US hyperscale facilities gives 300 GL/yr of operational water consumption, of which 74 GL is on-site cooling (scope 1) and 226 GL is water consumed generating the electricity (scope 2) — a 1:3 ratio. The two pathways have non-overlapping geographies: scope 1 hotspots are basins in the western and south-central US where cooling demand meets high Aqueduct stress; scope 2 hotspots are eastern grid regions with fossil-heavy supply. Scope 2 is far more concentrated — the top 3 of 24 hosting balancing authorities carry 59% of it, against the top 16 of 85 basins for 51% of scope 1. The result is an argument about institutions: cooling design and water sourcing are local decisions, electricity procurement is a regional one, and a single blended water footprint tells neither party what to do.

## Key Data

| Scenario | Electricity (TWh/yr) | Scope 1 (GL/yr) | Scope 2 (GL/yr) | Total (GL/yr) | Scope 2 share | Intensity (L/kWh) |
|---|---|---|---|---|---|---|
| Efficiency | 96.6 | 16.8 | 188.1 | 204.9 | 91.8% | 2.12 |
| **Baseline** | **115.9** | **74.2** | **225.7** | **299.9** | **75.3%** | **2.59** |
| High-load | 149.2 | 159.9 | 290.7 | 450.6 | 64.5% | 3.02 |
| No-hydro | 115.9 | 74.2 | 128.4 | 202.5 | 63.4% | 1.75 |

| Parameter | Efficiency / Baseline / High-load |
|---|---|
| Utilisation | 0.55 / 0.66 / 0.85 |
| PUE | 1.15 / 1.25 / 1.40 |
| WUE (L/kWh IT) | 0.2 / 0.8 / 1.5 |

Generation water-consumption factors (L/kWh): coal 1.9, gas 0.7, nuclear 2.5, **hydro 8.0**, wind 0.0, solar 0.1, other 1.0.

| Result | Value |
|---|---|
| Inventory | 472 facilities, 20,041 MW hyperscale nameplate capacity |
| Scope 1 concentration | top 16 of 85 basins = 51% |
| Scope 2 concentration | top 3 of 24 balancing authorities = 59% |
| Top scope 2 BAs | BPA 24.2%, PJM 21.3%, PacifiCorp West 13.8%, Grant County PUD 10.7% |
| Top scope 1 basins | Ohio 7.9%, two Virginia basins 7.1% and 5.4%, Iowa 3.4%, Oregon 3.4% |
| 25th-percentile BA grid water intensity | 1.41 L/kWh |
| External check | Google + Microsoft + Meta reported ~25 GL direct consumption in latest disclosures, broadly consistent with baseline scope 1 when scaled by capacity share |

## Methodology

Geospatial join of facility locations to balancing authorities, hydrologic basins and WRI Aqueduct stress. Scope 1 from WUE as defined in ISO/IEC 30134-9 (litres of site water consumption per kWh of IT electricity). Scope 2 from facility electricity demand × eGRID balancing-authority generation mix × technology-specific water-consumption factors. Water stress threshold is Aqueduct ≥ 3 (high to extremely high) in the basin or a touching neighbour. Hotspot classes combine above-median pathway burden with stress (scope 1) or with stress plus coal+gas share > 50% (scope 2).

Everything is modelled from public inventories and literature factors; no facility water data are used except as an external check. Reduction "benchmarks" are comparison arithmetic, explicitly not forecasts or feasibility assessments.

## Limitations and conflicts

Preprint, not yet peer reviewed. NIH-funded (R01MD016054, U24ES035309, R01ES037156, R01ES036731); no competing interests declared; code at https://github.com/gianguidi/hyperscale-water-geography.

The load-bearing assumption is hydro. Attributing reservoir evaporation to hydropower at 8.0 L/kWh puts BPA, PacifiCorp West, Grant County PUD and Douglas County PUD — four Pacific Northwest hydro utilities — at roughly half of national scope 2. Setting that factor to zero cuts scope 2 by 43% (226 → 128 GL) and the national total by a third. The authors flag the convention as contested and publish both, which is the right treatment, but it means the "75% of water is scope 2" headline should be read as "63-92% depending on scenario, and the hydro convention moves it most."

Three WUE values (0.2 / 0.8 / 1.5 L/kWh) are applied uniformly to all 472 facilities, so scope 1 geography is driven entirely by where capacity sits, not by actual cooling design. The authors say so. Facility electricity is derived from nameplate capacity and an assumed utilisation factor, not metered. Embodied water (chip fabrication, construction) is excluded.

## Relation to existing corpus

No direct overlap. This is the facility-resolved version of the scope 1 / scope 2 argument made nationally in `research/water/029-shehabi-2024-lbnl-direct-vs-indirect-water.md` and per-query in `research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md`. Note the three do not agree on the ratio: LBNL gets 1:12 indirect:direct for all US data centres (4.52 L/kWh indirect intensity), Guidi and Dominici get 1:3 for hyperscale (≈1.95 L/kWh implied), and the gap comes from different generation water factors and a lower assumed hyperscale WUE in LBNL. The divergence is itself a finding: the scope 2 multiplier is not settled. Independent of `research/water/028-ceres-2026-water-behind-the-watts.md`, which uses withdrawals; this one uses consumption throughout.

---
Retrieved: 2026-09-19
Search: WebSearch "2026 study data center siting water stressed basins" → arXiv 2607.02531; full PDF retrieved
