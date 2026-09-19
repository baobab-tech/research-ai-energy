# Water-Minimising Load Balancing Leaves the Worst-Hit Site at 1.62x the Fleet Average Water Footprint and Pushes Carbon Inequity to 2.18x

**Topic:** Water — regional disparity in AI inference water and carbon footprints across geographically distributed data centres; whether footprint-minimising scheduling reduces or amplifies that disparity
**Source:** Pengfei Li, Jianyi Yang (UC Riverside), Adam Wierman (Caltech), Shaolei Ren (UC Riverside), 2024
**Type:** peer-reviewed (ACM e-Energy '24, 15th International Conference on Future and Sustainable Energy Systems, Singapore, 4-7 June 2024; DOI 10.1145/3632775.3661938)
**URL:** https://arxiv.org/abs/2307.05494
**Published:** 2024-06 (arXiv v1 2023-06-20, v2 2024-05-02)

## Finding

Minimising an AI fleet's total water footprint concentrates the remaining footprint on particular sites. In an 18-day simulation of 10 geographically distributed data centres serving large language model inference, a scheduler that minimises total water consumption leaves the worst-affected location at 1.62 times the fleet average water footprint and drives the carbon inequity ratio to 2.18, the worst of every algorithm tested. Routing every request to its nearest data centre, the naive baseline, produces a lower water inequity ratio (1.45) than any of the energy-, carbon- or water-minimising schedulers. An equity-aware scheduler that explicitly minimises the maximum regional footprint brings the water ratio to 1.19 offline and 1.33 online while holding average water consumption and energy cost close to the alternatives.

The regional spread the paper works against is measured elsewhere and cited here: on-site cooling WUE stays below 1.0 L/kWh in cool climates and reaches a monthly average of 9.0 L/kWh in summer in Arizona, and Google's 2020 carbon-free energy share ran from 4% in Singapore to 94% in Finland, a 23-fold difference.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Max/average regional water footprint, water-minimising scheduler (GLB-Water) | 1.62 | Simulated; on-site cooling plus off-site generation water, 10 sites, 18 days, full routing flexibility |
| Max/average regional water, carbon-minimising scheduler (GLB-Carbon) | 1.91 | Same |
| Max/average regional water, energy-cost-minimising scheduler (GLB-Energy) | 1.71 | Same |
| Max/average regional water, nearest-data-centre baseline (GLB-Nearest) | 1.45 | Same |
| Max/average regional water, equity-aware offline optimum (eGLB-Off) | 1.19 | Same; requires complete knowledge of future workload, prices, carbon intensity and WUE |
| Max/average regional water, equity-aware online (eGLB) | 1.33 | Same; decisions made on sequentially revealed information |
| Max/average regional carbon, water-minimising scheduler | 2.18 | Same; highest carbon inequity of the nine algorithms tested |
| Max/average regional carbon, equity-aware offline optimum | 1.26 | Same |
| Fleet average water footprint per site, 18 days | 1,243.9 to 1,525.1 m3 | Simulated; total across 10 sites divided by 10 |
| Worst single-site water footprint, 18 days | 1,705.2 m3 (eGLB-Off) to 2,675.7 m3 (GLB-C2) | Simulated; maximum over the 10 locations |
| On-site cooling WUE, cool climate | below 1.0 L/kWh | Cited from prior work; ratio of on-site water consumption to IT energy |
| On-site cooling WUE, Arizona summer | 9.0 L/kWh monthly average | Cited from prior work (Ren, 2023) |
| Google carbon-free energy share, 2020 | 4% Singapore, 94% Finland (23x) | Cited from Google's own environmental report |
| Simulated site capacity | 500 servers, 4 NVIDIA A100 each, 2 kW peak per server, 1 MW IT per site | Assumed configuration |
| PUE | 1.1 | Assumed, constant across all 10 sites |

Ratios above 1.0 mean the worst-affected region carries more than its even share; 1.0 would mean every region carries the same footprint.

## Methodology

Trace-based simulation, not measurement of operating facilities. GPU power traces for the BLOOM language model over 23 September to 11 October 2022 were rescaled and distributed across 10 gateways with small per-time-zone perturbations. The 10 synthetic sites sit at Virginia, Georgia, Texas and Nevada in the United States; Belgium, the Netherlands, Germany and Denmark in Europe; and Singapore and Japan. Each is assumed to use a cooling tower. On-site WUE is computed hourly from wet-bulb temperature, derived from airport weather data, through an empirical formula taken from prior work. Off-site water is computed from hourly state or ISO-level fuel mix and per-fuel energy water intensity factors, so the water footprint spans both on-site cooling and generation. Hourly electricity prices come from ISOs for the US sites and country-level markets for Europe and Asia; European and Asian hourly fuel mixes were synthesised from US data because hourly mix data was not obtainable for those locations.

Two routing regimes are compared, full flexibility (any gateway to any site) and partial flexibility (each gateway reaches a subset). The offline optimum is solved in cvxpy with complete future information; the online algorithm uses dual mirror descent, with a regret bound proved against the offline optimum. Weights of 1,500 $/ton carbon and 60 $/m3 water set relative importance in the objective and are stated not to represent monetary costs.

## Limitations and conflicts

No conflict is apparent. The work is academic, from UC Riverside and Caltech, with no industry funding declared in the paper.

The construction is synthetic throughout. No real data centre's water consumption was measured; site capacities, server counts, PUE and cooling-tower assumption are stipulated, and the European and Asian fuel mixes are generated from US data. The inequity ratios are therefore properties of a model, and their absolute magnitude depends on the choice of 10 locations, the uniform 1.1 PUE and the uniform cooling-tower assumption. Applying air-side economisers or dry coolers at the hot-climate sites would compress the WUE spread that drives the result.

The inequity metric is maximum divided by average footprint. It treats regions as equally entitled irrespective of population, local water stress, or how much of the served demand originates there, so it measures dispersion of burden and not water stress. The 9.0 L/kWh Arizona figure and the 4%/94% carbon-free split are imported from other sources, not produced here.

The online algorithm's regret bound is asymptotic; the empirical gap to the offline optimum on water inequity is 1.33 against 1.19.

## Relation to existing corpus

Same research group as `research/water/001-li-2023-making-ai-less-thirsty.md` and `research/water/018-li-2025-cacm-ai-water-projections.md`, and a distinct paper from both: different author list (Wierman of Caltech in place of Islam of UT Arlington), different venue and different question. Files 001 and 018 quantify AI's aggregate water footprint; this one takes that footprint as given and asks how it distributes across sites. It reuses the WUE and EWIF machinery of 001.

Supplies the mechanism behind the geographic split reported in `research/water/032-guidi-dominici-2026-scope1-scope2-water-geography.md` and the regional WUE variation measured in `research/water/022-lei-2025-us-midsize-data-centers-wue.md`: hot, dry, cheap-power sites absorb disproportionate water burden partly because schedulers send work there.

Cuts against the implicit premise of `research/water/035-gaster-itif-2026-cooling-technology-water-energy-tradeoff.md` that national or aggregate water shares settle the question. A sub-1% national share is compatible with a single basin carrying several times the fleet average.

---
Retrieved: 2026-09-19
Search: arXiv abs page for 2307.05494, then full PDF of v2 via arxiv.org/pdf; ACM e-Energy '24 reference block confirmed in the PDF header
