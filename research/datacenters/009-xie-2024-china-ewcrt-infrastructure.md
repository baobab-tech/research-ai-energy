# Relocating Chinese data centres westward modelled to cut 2125 Mt CO2 by 2050, and 9500 Mt with PUE and green power

**Topic:** Data centres - siting, grid geography and growth
**Source:** Xie, Han & Tan (Tongji University; University of Nottingham Ningbo), 2024
**Type:** peer-reviewed
**URL:** https://doi.org/10.1057/s41599-024-02963-0
**Published:** 2024-03

## Finding

China's East-West Computing Resources Transmission Project is modelled as eight national data centre hubs and ten clusters, moving compute capacity from eastern demand centres to western regions with cheaper and cleaner power. Under a LEAP scenario model, the project scenario emits 2125 Mt CO2 less than business as usual cumulatively over 2020 to 2050, and an advanced scenario that also drives PUE to 1.1 after 2030 and raises the green electricity share cuts cumulative emissions by about 64%, or 9500 Mt CO2, against not building the project. The project scenario emits more CO2 than business as usual during the first decade, and the saving accrues only later in the period.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Infrastructure | 8 national hubs, 10 clusters | Policy design as announced; four hubs east, four west |
| PRO versus BAU cumulative saving | 2125 Mt CO2, 2020-2050 | Modelled; LEAP scenario difference, eight national hubs only |
| ADV versus BAU cumulative saving | 9500 Mt CO2, about 64%, 2020-2050 | Modelled; PUE 1.1 after 2030 plus raised green electricity share |
| BAU average PUE | 1.43 to 1.58 | Assumed parameter, from Greenpeace measured data |
| PRO PUE | below 1.25 east, below 1.2 west | Assumed policy target parameter |
| ADV PUE | 1.1 after 2030, for all hubs | Assumed; cited as Masanet et al.'s practical minimum |
| Rack power | 5-7 kWh/rack BAU; 6 kWh/rack PRO and ADV | Assumed parameter |
| Average IT load | 38-64% BAU; above 65% PRO and ADV | Assumed parameter |
| Grid emission factor | 0.071-0.992 tCO2/MWh; green grid 0.071 tCO2/MWh | Regional grid factors, applied by hub location |
| Rack growth | 20% per year 2020-2030 under BAU | Assumed parameter, projected from 1.24 million racks in 2016 to 5.9 million in 2022 |

The paper writes "metric tons (Mt)" throughout where the magnitude and the cited IEA comparator (300 Mt CO2 for data centres and networks in 2020) indicate megatonnes. Read every Mt figure here as megatonnes.

## Methodology

Scenario modelling with LEAP, 2020 as the base year and 2050 as the horizon, across three main scenarios (business as usual, project, advanced improvements) plus six sub-scenarios isolating PUE and green electricity. Emissions are computed from rack count, rack power, IT load, PUE and the local or national grid emission factor for each of the eight national hubs. Parameters come from official Chinese sources (NDRC, CAICT, CAC), Greenpeace measurements for PUE, and published studies. A separate fuzzy-set qualitative comparative analysis characterises which combinations of conditions distinguish data centre configurations, supporting the argument for differentiated strategies rather than contributing to the emissions estimate.

## Limitations and conflicts

Authors are at Chinese and China-based UK university business schools; no funding conflict is apparent from the record. The result is entirely a projection, and its size is driven by assumed parameters rather than by observation: rack growth of 20% per year, the PUE trajectory and the green electricity share are inputs, not findings. The 9500 Mt figure depends on a PUE of 1.1 across all hubs after 2030, which no fleet has demonstrated at scale. Only the eight national hubs are modelled, so the ten clusters and all non-hub capacity sit outside the boundary. Water, land, transmission losses and embodied emissions of the buildings and hardware are not modelled. AI-specific load is not separated from general data centre load, so nothing here isolates the effect of AI workloads.

## Relation to existing corpus

Provides the state-directed siting case against which market-sited data centre growth elsewhere in the corpus can be read. The assumed grid factor range of 0.071 to 0.992 tCO2/MWh shows the spread that carbon-aware routing exploits in ghg/014.

---
Retrieved: 2026-09-19
Search: OpenAlex DOI lookup, then the Nature Portfolio open access PDF
