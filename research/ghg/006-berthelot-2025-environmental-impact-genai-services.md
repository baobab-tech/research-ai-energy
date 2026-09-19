# Full-service LCA puts one year of Stable Diffusion at 463 t CO2e, with terminals and networks at 45% of it

**Topic:** GHG emissions - service-level LCA, inference and embodied share
**Source:** Berthelot, Caron, Jay & Lefèvre (ENS de Lyon, Inria, Université Grenoble Alpes), 2025
**Type:** peer-reviewed
**URL:** https://doi.org/10.1145/3725984
**Published:** 2025-06

## Finding

A life cycle assessment of Stable Diffusion run as an online service for one year, covering 75 million visits and 150 million generated images, gives 463 t CO2e. The dominant result is not that inference outweighs training: user terminals and networks account for more than 85% of the abiotic depletion impact, more than 30% of the primary energy footprint and 45% of the carbon footprint, which places nearly half the carbon outside the data centre entirely. Training electricity is estimated by replicating a fraction of the real training on instrumented hardware and extrapolating by linear regression, and the resulting estimate is 6% below the TDP-based estimate that the literature normally uses. Water is deliberately excluded for lack of reliable data.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Functional unit | one year of Stable Diffusion as a service, 75M visits, 150M images | Measured traffic August 2022 to August 2023; half of visits assumed to yield one generation of four 512x512 images |
| Global warming potential | 463 t CO2e | LCA; manufacturing plus use phase across data centre, web hosting, storage, networks and terminals |
| Terminals and networks share of GWP | 45% | Same LCA boundary |
| Terminals and networks share of abiotic depletion | above 85% | Same LCA boundary |
| Terminals and networks share of primary energy | above 30% | Same LCA boundary |
| Stable Diffusion v1-1 training energy | 4.70e2 kWh on 1 node, 1.50e4 kWh on 32 nodes, 2.37e5 steps at 256px | Measured on one node with an external power meter, extrapolated |
| Stable Diffusion v1-4 training energy | 4.01e2 kWh (1 node), 1.28e4 kWh (32 nodes), 2.25e5 steps at 512px | Same method |
| Stable Diffusion v1-5 training energy | 1.06e3 kWh (1 node), 3.39e4 kWh (32 nodes), 5.95e5 steps at 512px | Same method |
| TDP versus power-meter estimate | TDP 6% higher for v1-1 training | Direct comparison on the same workload |
| Software power meter versus external meter | about 20% apart per step, 25% at full training scale | Measured, Sirius and Gemini clusters |
| Water | not assessed | Explicitly excluded for lack of reliable data and because impact is contextual |

## Methodology

ISO 14040/14044 LCA over three impact categories: global warming potential, abiotic depletion potential for minerals and metals, and primary energy. Inventory data come from ADEME Base Empreinte for electricity mixes, NegaOctet for networks and terminals, and Boavizta for data centre equipment, the last covering manufacturing and use phases only. Training electricity is estimated by replicating Stable Diffusion v1-1 training on one node of the Grid'5000 Sirius cluster (Nvidia DGX A100, 8 A100-40GB) with an Omegawatt external meter at 0.1 W and 1 Hz plus the ALUMET software meter at 2 Hz, averaging seven runs, then fitting a linear regression of energy against training steps (R² above 0.99) and scaling to the developers' published step counts. The US national average electricity mix is applied to training and inference; a population-weighted mix is applied to terminals and networks. Code and data are published.

## Limitations and conflicts

Funded by ANRT under a CIFRE industrial doctoral agreement (2021/0576), by MIAI (ANR19-P3IA-0003) and by the BATE project of the Auvergne-Rhône-Alpes region; experiments ran on the publicly funded Grid'5000 testbed. The CIFRE scheme pairs a doctoral student with a company, and the CACM article does not name the partner. The authors state their GPU manufacturing footprints are underestimated, being derived from a CPU-oriented method. Training data production is excluded as too opaque. Water is excluded. The functional unit is a single open-weights image model, one to three orders of magnitude smaller than commercial text services, so the 463 t CO2e total does not transfer to ChatGPT-scale systems. Visit counts are external traffic estimates and the half-of-visits assumption is not validated. Network impact attribution is itself questioned by the authors, who note that marginal data transfer over fixed networks may add little electricity.

## Relation to existing corpus

Contradicts the common framing that AI emissions sit inside the data centre: 45% of carbon here falls on user terminals and networks. The training figures are measured by power meter, giving an instrumented comparator for the TDP-derived training numbers reproduced in ghg/001.

---
Retrieved: 2026-09-19
Search: OpenAlex DOI lookup; HAL and the ACM DL refused automated requests, so the full article text was read from the Internet Archive capture of cacm.acm.org
