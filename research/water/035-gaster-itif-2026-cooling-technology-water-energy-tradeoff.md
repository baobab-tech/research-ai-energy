# Quantified Cooling Trade-Offs: Dry Cooling Cuts Water >90% for a 1-1.5% Output Penalty; Hybrid Cuts Evaporation 75%; and the LBNL Indirect Figure Turns on Hydro

**Topic:** Water — cooling technology water/energy trade-off; critique of the indirect-water multiplier
**Source:** Robin Gaster, Information Technology and Innovation Foundation (ITIF), 2026
**Type:** think-tank report
**URL:** https://itif.org/publications/2026/07/06/the-data-center-water-problem-is-soluble/
**Published:** 2026-07-06

## Finding

Gaster puts numbers on the water-energy trade-off that CRS and most academic sources describe only directionally. For power-plant cooling: dry cooling cuts water consumption by more than 90% but takes 1-1.5% of plant output to run its fans against 0.5% for a wet tower, and degrades sharply above 80°F — exactly when demand peaks; hybrid wet/dry designs cut annual evaporative losses up to 75%; zero-liquid-discharge with high-recovery reverse osmosis costs under 0.1% of annual electricity output. For data-centre cooling, he argues closed-loop direct-to-chip is already reaching near-zero water. Separately, he attacks LBNL's indirect-water figure on two grounds: LBNL excludes power purchase agreements and behind-the-meter generation, and it includes hydropower reservoir evaporation. Excluding hydro, USGS and NREL-type thermoelectric factors give 0.47 gal/kWh (1.78 L/kWh) against LBNL's implied 1.19 gal/kWh (4.52 L/kWh).

## Key Data

### Cooling technology trade-offs

| Technology | Water effect | Energy effect |
|---|---|---|
| Once-through cooling | Massive withdrawal, low consumption | Minimal energy penalty; lowest capital cost |
| Wet recirculating tower | Baseline evaporative loss | 0.5% of plant output |
| Dry cooling | **>90% water reduction** | **1-1.5% of plant output**; performance degrades sharply above 80°F |
| Hybrid wet/dry | **Up to 75% reduction in annual evaporative loss** | Between the two; avoids full all-dry cost |
| Zero-liquid-discharge (high-recovery RO on tower blowdown) | Recovers and recycles purged concentrate | **<0.1% of annual electricity output** |
| Liquid direct-to-chip (closed loop) + external dry coolers | Near zero | Higher than evaporative; Nvidia Rubin runs loops up to 113°F |
| Two-phase immersion | Near zero | Blocked on supply chain: 3M exited PFAS dielectric fluids; Chemours alternatives not yet validated |
| Rear-door heat exchanger | Closed loop; secondary loop may still use evaporative towers | Retrofit path for existing air-cooled halls |

### Indirect water intensity — competing factors

| Source | Value | Includes hydro? |
|---|---|---|
| LBNL 2024 | 3.15 million gal/day per TWh (≈1.19 gal/kWh ≈ 4.52 L/kWh) | **Yes** |
| USGS 2015, once-through | 1.2 million gal/day per TWh | No |
| USGS 2015, recirculating | 1.4 million gal/day per TWh | No |
| USGS + NREL-type, thermoelectric average | **0.47 gal/kWh (1.78 L/kWh)** | No |
| Pacific Northwest (hydro-heavy) | 2.1 gal/kWh | Yes |
| California (solar-heavy) | 0.13 gal/kWh | |

One additional GWh at 0.47 gal/kWh = 474,230 gallons; ~4 billion gallons/yr for a sustained 1 GW load.

### National scale

| Metric | Value |
|---|---|
| US DC direct water consumption, 2023 | 17.4 billion gallons (LBNL) |
| US DC indirect water consumption, 2023 | 211 billion gallons (LBNL), ~12x direct |
| Direct + indirect as share of US water consumption | **<1%** against USGS national consumptive-use assessment (covering ~90% of withdrawals) |

## Methodology

A policy synthesis. No new measurement. Numbers are drawn from LBNL 2024, USGS national assessments, and vendor announcements (Nvidia, Microsoft). The argument: water is regulated by states, watershed conditions differ, and the correct instrument is state-level facility disclosure plus technology-neutral water-performance standards (gallons per MWh of IT load, calibrated by facility size and climate zone, escalating in high-stress basins, with credit for reclaimed water and required drought curtailment plans), not federal mandates.

## Limitations and conflicts

ITIF is a technology-industry-aligned think tank; its historical funders include major technology companies. This report is unfunded-disclosure — neither the report page nor the author note states who paid for it. The author is ITIF's own research director and has published a prior ITIF report arguing data-centre energy demand "is not necessarily a problem." Read the conclusions as an advocacy position with its evidence checkable, not as neutral assessment.

Specific issues:
- **The zero-water cooling claims are vendor announcements**, not measurements: Nvidia's Rubin "can use liquid cooling to reach zero water consumption" and Microsoft's design "will consume zero water" are both forward-looking statements about products, sourced to company communications. No deployed WUE figure is given for either. This contradicts LBNL's own modelled national trajectory (`research/water/029-...`), which has average site WUE *rising* to 0.45-0.48 L/kWh after 2023 partly because of liquid-cooled systems. Gaster does not address that.
- **The PPA critique cuts both ways.** Arguing LBNL overstates indirect water because operators contract renewables assumes contractual attribution reflects the physical water consumed at the plants actually serving the load. Annual REC matching does not; hourly matching would come closer.
- **The <1% national share conflicts with CRS R49057**, which puts *direct* consumption alone at ~2% of US water consumption (citing AWWA, Oct 2025). Both cannot be right. The denominators differ (USGS consumptive-use assessment covering ~90% of withdrawals vs an unspecified AWWA basis), which is precisely the kind of unstated-denominator problem this literature keeps producing.
- The report cites a "National Laboratory of the Rockies (NLR)"; no such laboratory exists. This is almost certainly NREL, and the citation should be checked before the 0.47 gal/kWh figure is relied on.
- Dry cooling's failure above 80°F is stated but not quantified: no capacity-derate curve, no hours-per-year exposure.

## Relation to existing corpus

No direct overlap. Supplies the quantified cooling trade-off that `research/water/025-li-zhu-2025-data-center-liquid-cooling-review.md` and `research/water/026-kim-2025-immersion-cooling-high-density-servers.md` describe only qualitatively, and adds the supply-chain constraint on two-phase immersion (3M's PFAS exit) that excerpt 026 does not mention. Directly disputes the indirect figure in `research/water/029-shehabi-2024-lbnl-direct-vs-indirect-water.md`. Its 0.47 gal/kWh = 1.78 L/kWh thermoelectric factor independently corroborates the 1.80 L/kWh EWIF used in `research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md` and confirms across three independent sources that the hydro-attribution convention, not the thermoelectric factor, is what moves the indirect-water estimate.

---
Retrieved: 2026-09-19
Search: WebSearch "AGU Advances 2026 data center water" → itif.org; full report text extracted from the publication page
