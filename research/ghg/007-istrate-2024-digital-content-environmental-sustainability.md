# A full-boundary LCA puts data-centre operation at 20-30% of the climate impact of consumer digital services, behind end-user device manufacturing at 32%

**Topic:** GHG emissions — lifecycle and embodied; where impact sits across devices, network and data centres
**Source:** Robert Istrate, Victor Tulus, Robert N. Grass, Laurent Vanbever, Wendelin J. Stark, Gonzalo Guillén-Gosálbez
**Type:** peer-reviewed (Nature Communications 15:3724)
**URL:** https://doi.org/10.1038/s41467-024-47621-w
**Published:** 2024-04

## Finding

An attributional life cycle assessment of the global average Internet user's annual digital content consumption puts the carbon footprint at 229 kg CO2-eq per person per year, about 3-4% of per capita anthropogenic emissions. The impact splits against the full infrastructure boundary: embodied impacts of end-user devices contribute an average 32% of climate impact, operation of end-user devices 22%, and operation of data centres 20-30%. Mineral and metal resources use is the category where digital consumption comes closest to its allocated limit, at 55% of the per capita carrying capacity, and 92% of that is embodied in end-user devices, driven by gold in integrated circuits. Decarbonising electricity cuts the climate share substantially and leaves the materials term almost untouched.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Carbon footprint, average user | 229 kg CO2-eq/person/year | attributional LCA, cradle-to-grave, devices + CPE + access/core network + data centres |
| Share of per capita anthropogenic GHG | 3-4% | against 6.0-7.6 t CO2-eq/person/year, 2019 |
| Share of 1.5 °C per capita carbon budget | 41% average (26% Norway to 61% India) | budget 501 kg CO2/person/year, IPCC AR6, 67% likelihood |
| Same share, 2.0 °C at 17% likelihood | 7% | sensitivity on budget choice |
| Same share, 1.5 °C at 83% likelihood | 55% | sensitivity on budget choice |
| Mineral and metal resources use | 55% of per capita carrying capacity | 92% of it embodied in end-user devices |
| Freshwater eutrophication | 20% of per capita carrying capacity | 45% embodied in end-user devices |
| Embodied end-user devices, climate | 32% of total climate impact | mainly electricity for wafer and IC manufacturing |
| Operation of end-user devices, climate | 22% average (1.3% Norway, 33% India) | varies with user-location grid |
| Operation of data centres | 20-30% of climate, acidification, eutrophication, particulate matter, ionising radiation, fossil, land and water use | global average data-centre electricity mix, not user location |
| Data-centre electricity geography | 39% North America, 34% Asia Pacific | share of global data-centre electricity consumed |
| Desktop computer share of embodied impacts | 28-57% depending on category | largest single device contributor |
| Desktop computer share of device operational impacts | 66.2% | laptop 18.4%, TV 8.8%, smartphone 3.7%, tablet 2.9% |
| Smartphone | 53% of time used, lowest impact of the five devices | per-device attribution |
| User archetype | 3,230 h/year total | 730 web, 894 social media, 833 video streaming, 566 music, 207 video conferencing |
| Traffic intensities | social media 0.31 GB/h; video streaming 1.3-2.4 GB/h | resolution-dependent for video |
| 1.5 °C-aligned 2030 power sector | climate share falls to 12% of carrying capacity | scenario, 78% power-sector decarbonisation |
| Same scenario, minerals and metals | rises to as much as 60% | scenario |
| Doubling device lifespan | minerals share falls 55% to 29% | scenario, current grid |

## Methodology

Attributional LCA conducted to ISO 14040/14044 across 16 impact categories, with results expressed against a per capita share of the Earth's carrying capacity under an equal-per-capita sharing principle. A single global user archetype was constructed from usage statistics for five content types and five device types, with time split across devices by observed preference. Each content type carries an average data traffic intensity in GB/h; network energy is allocated per unit of traffic in kWh/GB. Data-centre electricity is treated as globally distributed and independent of user location, while device and CPE electricity follows the user's national grid. Country sensitivities cover Norway, India, China, Australia, Poland and South Africa. Forward scenarios use 2030 power-sector pathways and a device-lifetime-extension case.

## Limitations and conflicts

Funded by NCCR Catalysis (Swiss National Science Foundation grant 180544); five of six authors are NCCR Catalysis affiliates. The authors declare no competing interests, and there is no industry funding or industry-supplied data. The study contributes no AI or machine-learning measurement: AI appears once, as a citation to other work, and the workload mix modelled is web, social media, video and music streaming and video conferencing. Its bearing on AI is as a boundary reference, since the 20-30% data-centre share is specific to streaming-dominated consumer traffic and cannot be carried over to accelerated compute, where the device-side term is near zero and the data-centre term dominates. A single global user archetype suppresses the very large variation in actual usage. Network energy is allocated per GB, an approach known to be sensitive to the assumed kWh/GB intensity and to overstate marginal traffic cost. The carrying-capacity denominator depends on an equal-per-capita sharing choice the authors acknowledge is contested, and the headline 41% figure moves between 7% and 55% purely on the choice of carbon budget probability.

## Relation to existing corpus

No direct overlap. The per-GB, per-user framing is orthogonal to the per-inference measurements in community/001 and to the facility-level reporting in policy/019 and policy/020.

---
Retrieved: 2026-09-19
Search: Nature Communications open-access PDF via DOI, text-extracted locally
