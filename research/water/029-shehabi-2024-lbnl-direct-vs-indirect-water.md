# US Data Centres 2023: 66 Billion Litres Consumed On-Site, ~800 Billion Litres Consumed Off-Site Generating Their Electricity

**Topic:** Water — on-site vs off-site water on a common consumption basis; national WUE trajectory
**Source:** Shehabi, Smith, Hubbard, Newkirk, Lei, Siddik, Holecek, Koomey, Masanet, Sartor — Lawrence Berkeley National Laboratory, 2024
**Type:** agency report (LBNL, prepared for US DOE under Public Law 116-260)
**URL:** https://eta-publications.lbl.gov/sites/default/files/2024-12/lbnl-2024-united-states-data-center-energy-usage-report_1.pdf
**Published:** 2024-12

## Finding

The off-site water consumed generating US data-centre electricity in 2023 was about 12 times the water consumed inside the facilities: ~800 billion litres against 66 billion litres. Both figures are **consumption** (water permanently removed from the immediate water cycle), so this is the like-for-like comparison that the withdrawal-based literature does not provide. LBNL also projects national average site WUE *rising* after 2023, from just over 0.36 L/kWh to 0.45-0.48 L/kWh, and attributes part of that rise to the increased water consumption of liquid-cooled AI systems — cutting against the claim that direct-to-chip liquid cooling is a water-saving technology at the facility level.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Direct water consumption, US DCs 2014 | 21.2 billion L | On-site (site WUE), 64% in internal DCs |
| Direct water consumption, US DCs 2023 | 66 billion L | On-site; hyperscale + colocation = 84% of total, internal DCs down to 12% |
| Direct water consumption, hyperscale 2028 | 60-124 billion L | Scenario range |
| Indirect water consumption, US DCs 2023 | ~800 billion L | At generation, by balancing-authority grid mix; **consumption**, not withdrawal |
| Ratio indirect : direct, 2023 | ~12 : 1 | Consumption basis |
| DC electricity, 2023 | ~176 TWh | 4.4% of US total |
| Indirect water intensity, DC grid mix 2023 | 4.52 L/kWh | National average for DC locations |
| Indirect water intensity, US electricity overall | 4.35 L/kWh | For comparison |
| Indirect GHG, US DCs 2023 | 61 billion kg CO2e (0.34 kg/kWh) | Same method |
| National average site WUE, through 2023 | just over 0.36 L/kWh | All US DCs, modelled |
| National average site WUE, 2028 | 0.45-0.48 L/kWh | **Rising**; attributed to hyperscale/colocation WUE increases and liquid-cooled systems |
| Hyperscale aggregate median WUE, 2023 | 0.32 L/kWh modelled (0.40 if adiabatic systems run at 0.2 L/kWh) | Simulated, not metered |
| Hyperscale self-reported WUE, similar systems | 0.1-0.3 L/kWh | Company-reported; LBNL notes system specifics unknown |
| National average PUE | 1.6 (2014) → 1.4 (2023) → 1.15-1.35 (2028) | |

## Methodology

IT equipment shipment and stock modelling feeds building-energy simulation of cooling systems by climate zone and facility type, producing modelled PUE and WUE by space type; these multiply IT energy to give on-site electricity and water. WUE here is site WUE — cooling-infrastructure water only — and LBNL states explicitly that this is distinct from "WUE source", the water consumed at electricity generation.

Indirect water uses county-to-balancing-authority assignment: EIA 930 hourly interchange between balancing authorities, EIA 923 plant-level generation, EIA plant water consumption, EPA emissions, following Siddik et al. (2024). This yields per-balancing-authority water-consumption intensity, applied to data-centre electricity by county.

Everything here is modelled, not metered. LBNL flags that the airside-economizer-with-adiabatic-cooling system is poorly characterised and its simulated WUE may be too low.

## Limitations and conflicts

Federally funded (DOE), authors are LBNL and academic (Koomey, Masanet); no industry funding declared. Two stated methodological limits bear on the water numbers:

1. The indirect calculation ignores power purchase agreements and behind-the-meter generation, assuming every data centre takes the local balancing authority's grid mix. For operators with large contracted renewable portfolios this overstates indirect water; for others it may understate it. LBNL says it is constrained by the absence of facility-level data.
2. On-site WUE is simulation output, not measurement, and the hyperscale figure is sensitive to an assumption LBNL itself calls uncertain (0.32 vs 0.40 L/kWh depending on how adiabatic systems are assumed to run).

Water source is not distinguished: reclaimed, non-potable and potable makeup water count identically.

## Relation to existing corpus

LBNL's June 2026 update (`../datacenters/016-lbnl-2026-us-dc-energy-2025-update.md`) revises
electricity and PUE but contains no water estimates; the word "water" appears twice in it, neither
time as a quantity. The 2023 figures here are LBNL's only water assessment and stand as the
national baseline, although the electricity figures underlying them (176 TWh) are revised to
192 TWh for 2024 in the newer report.

Otherwise no direct overlap — the corpus lacked this report's water content entirely. It supplies the consumption-basis counterpart to `research/water/028-ceres-2026-water-behind-the-watts.md`, whose 3.4-trillion-gallon headline is a withdrawal figure dominated by hydropower pass-through; LBNL's 12:1 indirect:direct ratio is the defensible version of the same claim. Ceres cites LBNL's 176 TWh and reports the 211-billion-gallon (≈800 billion L) indirect figure. It is the source of the WUE baseline that `research/water/022-lei-2025-us-midsize-data-centers-wue.md` (same LBNL group) extends to small and midsize facilities, and its national WUE trajectory runs against the near-zero-water cooling claims relayed in `research/water/035-gaster-itif-2026-cooling-technology-water-energy-tradeoff.md`: the modelled national figure goes up, not down, as liquid cooling arrives.

---
Retrieved: 2026-09-19
Search: WebSearch "LBNL 2024 United States Data Center Energy Usage Report water consumption"; PDF from eta-publications.lbl.gov, text extracted with pdftotext
