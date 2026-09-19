# Off-grid wind, solar, battery and gas microgrids for a 50 MW data centre model at 70–102 GBP/MWh and 0.021–0.074 tCO2eq/MWh, beating 2023 retail grid prices and 2023 average grid carbon intensity at five European sites

**Topic:** Data-centre infrastructure — off-grid power sourcing, renewable microgrids versus grid connection
**Source:** Rollinson, W.; Urquhart, A.; Thomson, M. — CREST, Loughborough University, 2025
**Type:** peer-reviewed (technoeconomic modelling)
**URL:** https://doi.org/10.3390/en18020382
**Source note:** Open-access PDF retrieved from https://mdpi-res.com/d_attachment/energies/energies-18-00382/article_deploy/energies-18-00382.pdf
**Published:** 2025-01

## Finding

WindPRO optimisation of stand-alone hybrid microgrids for a 50 MW flat-load hyperscale data centre at five European sites returns a levelised cost of energy utilised between 70 and 102 GBP/MWh and a carbon intensity between 0.021 and 0.074 tCO2eq/MWh, both below the grid equivalent at every site. The comparison basis determines the result and is narrower than the headline suggests: cost is measured against 2023 retail industrial electricity prices, the peak of the post-2022 European energy price spike, and carbon against 2023 annual average grid intensity held flat for 35 years. The authors state that if electricity prices returned to pre-2021 levels the economic advantage would be reduced, and that grid carbon intensity is expected to fall over the asset life, neither of which is modelled.

None of the five configurations is renewable-only. Every site carries 50 MW of reciprocating gas engine capacity, sized to meet full load, supplying between 8.0% of annual energy at Paris and 19.6% at Frankfurt. Gas combustion is the sole source of the operational emissions above.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Modelled load | 50 MW flat, 35-year life | Cooling fluctuation neglected; assumed under 10% of total energy |
| Sites | Frankfurt, Southwest England, Amsterdam, Paris, Dublin | Abstract says "London"; results tables use Southwest England |
| LCOEu | 70 (Dublin) – 102 (SW England) GBP/MWh | Modelled; cost of energy actually consumed by the data centre |
| LCOE (all generated energy) | 46 (Paris) – 78 (SW England) GBP/MWh | Lower than LCOEu because each system over-generates |
| LCOE of wind and solar alone | 28–42 GBP/MWh | Excludes battery and gas; the figure a PPA headline resembles |
| Carbon intensity | 0.021 (Paris) – 0.074 (Frankfurt) tCO2eq/MWh | Construction embodied + operational gas, over 35 years |
| Gas share of annual energy | 8.0% (Paris) – 19.6% (Frankfurt) | Modelled dispatch |
| Wind share | 32.1–53.2% | |
| Solar share | 24.4–30.0% | |
| Installed gas capacity | 50 MW at every site | Full load backup; removes need for diesel |
| Installed wind capacity | 73 (Dublin) – 172 (Paris) MW | |
| Installed solar capacity | 109 (Paris) – 194 (SW England) MW | |
| Battery power rating | 40.5–60.7 MW, each rated for 10 h/day | Over 80% of load in power terms |
| Wind capacity factor | 24% (Frankfurt) – 50% (Dublin) | Authors flag 39–50% at Amsterdam, Paris, Dublin as above the 30–35% expected for new European onshore wind |
| Solar capacity factor | 12–16% | |
| Land required | 173 (Dublin) – 628 (Paris) ha | Solar and wind assumed unable to share land |
| CAPEX | 422.5 (Dublin) – 529.5 (Amsterdam) GBP M | Authors note this potentially doubles a data-centre developer's expected CAPEX |
| 35-year total cost, hybrid | 658.1–959.3 GBP M | 3% interest rate |
| 35-year total cost, grid | 1,028.4 (Paris) – 2,168.8 (SW England) GBP M | At 2023 retail industrial electricity prices |
| Grid carbon intensity assumed | Paris 0.053; SW England 0.200; Amsterdam 0.283; Dublin 0.371; Frankfurt 0.400 tCO2eq/MWh | 2023 annual average, held constant for 35 years |
| Emissions reduction vs grid | 32% (Paris) – 88% (Dublin) | Against that flat 2023 average |
| Gas-only alternative | 0.197 MtCO2eq/yr at every site | 0.18 kgCO2eq/kWh fuel at 40% engine efficiency |
| Component CAPEX assumptions | Wind 1400 GBP/kW (2022); solar 615 GBP/kW (2020/2023); battery 950 GBP/kW + 170 GBP/kWh (2020/2021); gas 800 GBP/kW (2021) | Reference years as published, not harmonised to a single cost year |
| Embodied carbon assumptions | Wind 333; solar 400 kgCO2eq/kW; battery 200 kgCO2eq/kWh | From cited life-cycle literature |
| Sensitivity result | LCOEu and emissions stay below grid at all sites except Paris if wind output falls 30% | Shortfall assumed made up by gas |

## Methodology

EMD International WindPRO 4.0 sized and dispatched wind, solar, battery and gas for a constant 50 MW load at each site, optimising for LCOE. Wind farm layout used WindPRO's wake model and proprietary layout optimiser; solar assumed optimisable tilt and row spacing. The authors introduce LCOEu, levelised cost of energy utilised, which divides system cost by only the energy the data centre consumes rather than by all energy generated, so that curtailment and over-generation carry their cost. Comparators are three: the local grid at 2023 retail industrial prices and 2023 average grid carbon intensity; an on-site gas-only system; and published average European PPA prices (40 GBP/MWh private wire, 70 GBP/MWh sleeved or virtual).

## Limitations and conflicts

Funding: the authors state the research received no external funding and declare no conflicts of interest. All three are at Loughborough University's Centre for Renewable Energy Systems Technology, a renewable-energy research centre, which is a subject-matter alignment rather than a financial interest.

The cost comparison rests on a single year's retail prices at a historical maximum. The authors say directly that a return to pre-2021 electricity prices would reduce the advantage, and Figure 3 in the source shows the hybrid systems undercutting the grid only from 2021 onward. The carbon comparison is against grid *average* intensity, not marginal or hourly intensity, and holds the 2023 value fixed across a 35-year life while acknowledging that renewable penetration will lower it. At Paris the margin is already thin: 0.021 against a French grid at 0.053, so a decarbonising grid closes it fastest where nuclear is already dominant.

The wind capacity factors are the weakest physical input. Values of 38–50% at Amsterdam, Paris and Dublin sit above the 30–35% the authors cite as expected for new European onshore wind; they attribute this to hub heights above 150 m selected in WindPRO, "achievable though not yet common". The sensitivity analysis covers a 30% wind shortfall but makes it up with gas, which raises emissions along a path the headline range does not include.

Cost inputs are not harmonised to a common price year, mixing 2020, 2021, 2022 and 2023 references. Battery degradation is excluded from the model and battery storage costs are excluded from the LCOE calculation, both stated by the authors. Cooling is excluded from the load on the assumption it is under 10% of total energy, which amounts to assuming PUE near 1.1 and is optimistic against the modelled 1.16–1.43 range in `004-kim-2024-data-center-pue-economizers.md`. Land is costed but planning, grid-independence permitting, air permits for the gas engines, and construction lead times are not.

The emissions table is internally inconsistent. Its "operational emissions" column (0.436, 0.396, 0.250, 0.307 MtCO2eq/yr for Southwest England, Amsterdam, Paris and Dublin) cannot be reconciled with the same table's own carbon intensity and annual energy production, which imply roughly 0.028, 0.025, 0.016 and 0.020; only the Frankfurt row (0.039) is self-consistent. The carbon intensity and 35-year total columns are mutually consistent and are the values reproduced above.

## Relation to existing corpus

Directly countered in practice by `025-selc-earthjustice-2026-xai-memphis-unpermitted-turbines.md`. The largest off-grid AI campus actually built chose unabated gas at roughly 1.2 GW rather than a renewable hybrid, and its binding constraint was Clean Air Act permitting rather than levelised cost. That case is the missing variable in this model: the paper prices gas fuel and carbon but not air permitting, siting opposition or the possibility that a developer under interconnection pressure will pick the fastest dispatchable option rather than the cheapest lifetime one.

The paper argues PPAs are a partial solution at best: the consumer must top up from the grid whenever contracted wind and solar are not generating, and the grid is carbon-intensive precisely then, so a certificate-based 100%-renewable claim does not describe the electricity consumed. This is the same gap between contracted and delivered clean power documented in `020-carnegie-2026-hyperscaler-nuclear-13gw-zero-operating.md` and `../washing/027-trencher-2024-offset-quality-base-rate.md`.

---
Retrieved: 2026-09-19
Search: DOI 10.3390/en18020382; open-access PDF via mdpi-res.com
