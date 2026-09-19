# Water

16 excerpts, every one verified against its source.

[Full index](_index.md)

## Boundaries decide the arguments

Almost every apparent conflict in this literature is a boundary mismatch:

- **Withdrawal** is water taken from a source and may return to the basin. **Consumption** is
  water removed from it. For electricity generation the two differ by about an order of magnitude.
- **Scope 1** is water evaporated in the facility's own cooling. **Scope 2** is water consumed
  generating its electricity, and it is the larger term.

## Per-request figures, like for like

| Source | Value | Scope |
|---|---|---|
| [Google 2025](017-google-2025-gemini-water-measurements.md) | 0.26 mL | 1 |
| [Li et al. 2023](001-li-2023-making-ai-less-thirsty.md) | 2.200 mL | 1 |
| Li et al. 2023 | 14.704 mL | 2 |
| Li et al. 2023 | 16.904 mL | 1+2, US average; 7.107 (Ireland) to 47.506 (Washington) |
| [Sharma et al. 2026](027-sharma-2026-water-cost-of-intelligence-boundary.md) | 0.725 mL | 1+2, Google's prompt |

**The like-for-like comparison is 0.26 mL against 2.200 mL, a factor of about 8.5.** The 40x to
100x gap quoted elsewhere sets a scope-1 figure against a scope 1+2 total.

The figure "10 to 25 mL per query" appears in no version of Li et al. It was back-computed from
April 2023 preprint wording that the authors replaced with "10 to 50 medium-length responses".

Google's 0.26 mL is not metered per prompt. It is measured IT energy multiplied by a fleet-average
WUE of 1.15 L/kWh under ISO/IEC 30134-9 Category 2, which counts on-site freshwater only and
excludes generation water, embodied water and all training water.

## Training

GPT-3 training consumed **5.439 million litres**: 0.708 million on-site and 4.731 million
generating the electricity, which is 87% of the total
([001](001-li-2023-making-ai-less-thirsty.md)). The quoted "700,000 litres" is the scope-1 term.

## Projections

Global AI is projected to **withdraw** 4.2 to 6.6 billion m³ in 2027 and to **consume** 0.38 to
0.60 billion m³ ([018](018-li-2025-cacm-ai-water-projections.md)). About 97% of the withdrawal
is off-site power-plant cooling. The derivation applies US-average intensity factors to a global
electricity projection at an assumed PUE of 1.1, with no geographic distribution.

## The indirect multiplier is unsettled

Scope 2 water against scope 1:

| Source | Ratio | Basis |
|---|---|---|
| [LBNL 2024](029-shehabi-2024-lbnl-direct-vs-indirect-water.md) | 12:1 | 66 GL direct, ~800 GL indirect |
| [Guidi & Dominici 2026](032-guidi-dominici-2026-scope1-scope2-water-geography.md) | 3:1 | 472 facilities; 1.7:1 without hydro allocation |
| [CRS / IEA 2026](034-crs-2026-data-centers-water-faq.md) | 1.5:1 | 40:60 direct to indirect |

The spread turns on whether reservoir evaporation is allocated to hydropower. Three independent
sources converge on 1.78 to 1.80 L/kWh for thermoelectric generation excluding hydro. The choice
can reverse regional rankings 94-fold.

## Scale depends on where it is measured

Direct data-centre water is about 2% of US consumptive use
([034](034-crs-2026-data-centers-water-faq.md)). Peak-day demand at one Meta campus reaches 134%
of its host utility's entire delivery capacity, with burden across ten US sites spanning 0.002 to
1.34 ([033](033-akinade-2026-water-consumption-impact-utility-burden.md)).

Load balancing redistributes the burden without removing it. Water-minimising placement still
leaves the worst-hit site at 1.62x the fleet average, and it is the worst strategy for carbon at
2.18x ([019](019-li-2023-environmental-equity-regional-water.md)).

Ceres reports 3.4 trillion gallons **withdrawn** across seven states in 2024, about 78% of it
hydropower pass-through ([028](028-ceres-2026-water-behind-the-watts.md)).

## Disclosure

Microsoft reports 13,266 ML withdrawn and 8,170 ML consumed in FY25 against 14.2 million m³
replenished, reaching "water positive" as a global aggregate. Its own site table shows
replenishment delivered at 7 of 28 locations, concentrated where withdrawal is small
([030](030-microsoft-2026-fy25-site-level-water.md)). Google's consumption rose 34% to 10,869
million gallons, with replenishment covering 78% of **freshwater** consumption and 71% of total
([031](031-google-2026-fy2025-water-disclosure.md)).

Electricity-related water is 75% of operational water consumption across 472 US hyperscale
facilities, and it lands in different basins from the facilities themselves
([032](032-guidi-dominici-2026-scope1-scope2-water-geography.md)).

## Cooling

Dry cooling cuts water by more than 90% for a 1 to 1.5% output penalty; hybrid cuts evaporation
75%; zero-liquid-discharge reverse osmosis costs under 0.1% of output
([035](035-gaster-itif-2026-cooling-technology-water-energy-tradeoff.md)). Vendor near-zero-water
claims in that source are announcements, not measurements, and LBNL projects national site WUE
rising to 0.45 to 0.48 L/kWh.

US midsize data centres improved PUE from 1.46-1.83 to 1.43-1.76 while WUE **rose** from
0.52-0.86 to 0.56-0.96 L/kWh, by adopting water-cooled chillers
([022](022-lei-2025-us-midsize-data-centers-wue.md)). Neither figure is measured; both weight
published per-cooling-system values by modelled county server counts.

## Siting conflict

Google's Cerrillos facility was permitted for 169 L/s in a drought-stricken Santiago district. A
non-binding referendum returned 38% approve and 49% reject, and a 2019 environmental tribunal
found scientific uncertainty on aquifer availability
([002](002-lehuede-2024-elemental-ethics.md)).

## Gaps

- No independent verification of Google's 0.26 mL beyond reconstruction from Google's own inputs.
- No independent assessment of water-positive pledge delivery. Corporate self-report only.
- Meta has published no FY2025 water data; its latest covers calendar 2024.
- No source establishes that liquid or immersion cooling reduces water consumption. The claim was
  asserted in earlier secondary summaries and is absent from the primary cooling literature.
