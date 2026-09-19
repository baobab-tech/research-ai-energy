# One Meta Campus's Peak-Day Cooling Demand Equals 134% of Its Host Utility's Delivery Capacity; Burden Across Ten US Sites Spans Three Orders of Magnitude

**Topic:** Water — utility-scale siting burden; why national volumetric totals and WUE miss the binding constraint
**Source:** Akinade, Amanambu, Frame (University of Alabama) and Ren (UC Riverside), 2026
**Type:** preprint (arXiv, cs.CY) — review with original index and site analysis
**URL:** https://arxiv.org/abs/2606.21760
**PDF:** https://arxiv.org/pdf/2606.21760
**Published:** 2026-06-19

## Finding

The authors define the Water Consumption Impact index as a facility's peak-day consumptive cooling demand divided by its host public water system's maximum deliverable capacity, and compute it for ten US sites. Values run from 0.002 (Henderson NV, inside the Southern Nevada system) to 1.34 (Meta, Lebanon, Indiana), where a single facility's worst-day demand exceeds the entire host utility's 17.4 ML/d capacity. The argument is that the binding constraint is peak-day delivery capacity, not annual volume or watershed supply: data centres combine consumptive ratios of 0.70-0.90 against a 12% public-supply average with peaking factors of 6 to over 30 against 1.5-2.5 for other users, so infrastructure sized for average demand fails on the peak day even where raw water is abundant. Shaolei Ren, co-author of the Li et al. "Making AI Less Thirsty" work, is a co-author here.

## Key Data

### Site inputs and WCI (W = average daily withdrawal ML/d, r = consumptive ratio, PF = peaking factor)

| Site | Operator | W (ML/d) | r | PF | C_peak (ML/d) | Notes |
|---|---|---|---|---|---|---|
| Lebanon, IN | Meta | 4.81 | 0.77 | 6.3 | 23.32 | **WCI 1.34** vs 17.4 ML/d host capacity; 0.25 against the planned 94.6 ML/d dedicated supply |
| Council Bluffs, IA | Google | 14.62 | 0.716 | 6.5 | 68.02 | Largest absolute footprint, ~9,220 household-equivalents |
| Mayes Co., OK | Google | 11.49 | 0.752 | 2.5 (default) | 21.59 | ~7,610 household-equivalents |
| The Dalles, OR | Google | 4.78 | 0.784 | 2.21 | 8.28 | ~3,301 household-equivalents |
| Douglas Co., GA | Google | 4.60 | 0.826 | 2.5 (default) | 9.50 | Highest r — warm-humid climate |
| Mount Pleasant, WI | Microsoft | 0.087 | 0.77 (assumed) | 30 | 2.01 | PF-dominated |
| Botetourt Co., VA | Google | 7.57 | 0.77 (assumed) | 2.5 (default) | 14.57 | |
| Memphis, TN | xAI | 3.79 | 0.77 (assumed) | 4.5 (placeholder) | 13.12 | Colossus; source is Protect Our Aquifer |
| Midlothian, TX | Google | 2.29 | 0.825 | 2.5 (default) | 4.72 | |
| Henderson, NV | Google | 3.73 | 0.576 | 2.5 (default) | 5.37 | **WCI 0.002** |

### Structural numbers cited

| Metric | Value |
|---|---|
| Data-centre consumptive ratio | 0.70-0.90, vs 12% public-supply average |
| Data-centre peaking factor | 6 to >30, vs 1.5-2.5 for other users |
| National DC share of public withdrawals by 2030 | 0.6-1.1% |
| Dry-cooling energy penalty | 25-35% |
| Location vs technology effect on hydrologic stress | location ~4,897x larger |
| Northern Virginia aggregate DC peaking factor | 10; consumptive use rises 9% → 12% of regional total in summer |
| Drought Amplification Factor | ~1 on large regulated rivers to >100 in flashy desert systems |
| Per-query water across architectures | <4 mL to >200 mL |
| GPT-3 training | ~700,000 L on-site; 5.4 million L including electricity-related |
| WCI 100% breach dates at g = 0.13/yr | Council Bluffs 2029, Mayes Co. 2029, The Dalles 2030, Douglas Co. 2034, Wisconsin 2035 |

### Water as a siting constraint (documented cases)

Uruguay — Google redesigned a hyperscale facility to air cooling after the worst drought in seven decades and opposition over a projected 7.6 ML/d potable demand. Chile — an environmental court partially overturned Google's permit in 2024. Netherlands and Ireland — moratoriums on new construction citing cumulative water and energy pressure. Lebanon, Indiana — a six-year phased infrastructure expansion before the Meta campus reaches full water capacity.

## Methodology

WCI = C_peak / K, decomposed as (W/K) × r × PF, so each factor maps to a lever: demand scale to siting, consumptive ratio to cooling technology, peaking factor to workload scheduling and thermal storage. Household equivalence uses 0.4146 ML/household/year (~1,136 L/day). Forward projection applies g = 0.13/yr (lower bound of projected US data-centre energy growth) with host capacity K held constant.

Google site inputs (W, consumption, PUE, and therefore r) are taken directly from Google's own per-campus disclosures, which are independently assured by EY. For Meta, Microsoft and xAI, r = 0.77 is assigned from a literature weighted mean. Literature base is 97 sources, tiered peer-reviewed > government > corporate self-report > investigative reporting.

## Limitations and conflicts

Preprint, not peer reviewed; no funding statement located in the PDF. Author affiliations are academic.

The WCI numbers are not uniformly measured. Four of ten sites use a default peaking factor of 2.5 because none is disclosed; xAI Memphis uses a 4.5 "placeholder"; three sites use an assumed consumptive ratio of 0.77; the Wisconsin PF of 30 comes from a public-radio report via a secondary analysis. The headline 1.34 for Lebanon rests on an analytically recomputed peaking factor from Han et al., not a metered one, and the authors themselves show it falls to 0.25 against the purpose-built supply being built for the site — so "exceeds host capacity" is true of the current municipal system, not of the infrastructure being provisioned. The 2029-2035 breach projections hold host capacity fixed and exclude the utility expansions the authors acknowledge are planned, which they state would reduce projected WCI. The "location effect is 4,897x the technology effect" figure is carried from a single cited source, not computed here.

The framing is advocacy-adjacent: the paper argues for a governance regime and a new indicator it proposes. The burden analysis stands on its own arithmetic; the "adaptive pathway" (AI improving water systems) is described by the authors themselves as conditional potential, not demonstrated.

## Relation to existing corpus

No direct overlap. Supplies the utility- and community-scale evidence the corpus lacks, and is the counterweight to the national aggregates in `research/water/032-guidi-dominici-2026-scope1-scope2-water-geography.md` and `research/water/029-shehabi-2024-lbnl-direct-vs-indirect-water.md`: at 0.6-1.1% of national public withdrawals, data centres are nationally small and locally decisive. Extends `research/water/019-li-2023-environmental-equity-regional-water.md` (same research lineage — Ren is a co-author of both) from regional disparity to host-utility capacity. Its critique of WUE — location-agnostic, IT-energy denominator, seasonally variable and therefore selectively reportable — applies directly to the fleet WUE figures in `research/water/030-microsoft-2026-fy25-site-level-water.md` and `research/water/031-google-2026-fy2025-water-disclosure.md`.

---
Retrieved: 2026-09-19
Search: WebSearch "2026 data center water stressed basins aquifer" → arXiv 2606.21760; full PDF retrieved
