# Water

26 excerpts on data-centre water: the per-request figures and what boundary each uses, cooling
technology, corporate disclosure, and site-level constraint.

[Full index](_index.md)

## Boundaries first

Almost every apparent conflict in this literature is a boundary mismatch. Two distinctions decide
the arguments:

- **Withdrawal** is water taken from a source and may return to the basin. **Consumption** is
  water evaporated or otherwise removed. They differ by roughly an order of magnitude for
  electricity generation.
- **Scope 1** is water evaporated in the facility's own cooling. **Scope 2** is water consumed
  generating the electricity the facility draws. Scope 2 is the larger term.

## Per-request figures, compared like for like

| Source | Value | Scope | Note |
|---|---|---|---|
| [Google 2025](017-google-2025-gemini-water-measurements.md) | 0.26 mL | 1 | median Gemini text prompt; IT energy × fleet WUE 1.15 L/kWh, Category 2 |
| [Li et al. 2023](001-li-2023-making-ai-less-thirsty.md) | 2.200 mL | 1 | per medium request, US average, Microsoft assumptions |
| Li et al. 2023 | 14.704 mL | 2 | generation water, US average |
| Li et al. 2023 | 16.904 mL | 1+2 | total; range 7.107 mL (Ireland) to 47.506 mL (Washington) |
| [Sharma et al. 2026](027-sharma-2026-water-cost-of-intelligence-boundary.md) | 0.725 mL | 1+2 | Google's prompt with generation water at 1.80 L/kWh |

**The like-for-like comparison is 0.26 mL against 2.200 mL, a factor of about 8.5.** Comparing
Google's scope-1 figure against Li et al.'s scope 1+2 total produces the 40x to 100x gap quoted
elsewhere, and that comparison is not valid.

The figure "10 to 25 mL per query" does not appear in Li et al. It was back-computed from the
April 2023 preprint wording "500 mL per 20-50 queries", which the authors replaced in v5 and in
the published CACM text with "10 to 50 medium-length responses".

Google's 2026 report derives its water number by applying a 2024 fleetwide WUE to a May 2025
energy measurement and publishes no WUE figure anywhere in the document
([031](031-google-2026-fy2025-water-disclosure.md)).

## Training

GPT-3 training consumed **5.439 million litres** total: 0.708 million on-site (scope 1) and 4.731
million off-site generating the electricity (scope 2), which is 87% of the total
([001](001-li-2023-making-ai-less-thirsty.md)). The widely-quoted "700,000 litres" is the scope-1
term alone.

## Projections

The projection of **4.2 to 6.6 billion m³ of global AI water by 2027 is withdrawal, not
consumption.** Projected consumption is **0.38 to 0.60 billion m³**, an order of magnitude
smaller, and about 97% of the withdrawal figure is off-site power-plant cooling
([018](018-li-2025-cacm-ai-water-projections.md)). The derivation applies US-average water
intensity factors to a global electricity projection (de Vries 2023, 85-134 TWh) at an assumed
PUE of 1.1, with no geographic distribution.

## The indirect multiplier is unsettled

Scope 2 water against scope 1:

| Source | Ratio | Basis |
|---|---|---|
| [LBNL 2024](029-shehabi-2024-lbnl-direct-vs-indirect-water.md) | 12:1 | 66 GL direct, ~800 GL indirect, 4.52 L/kWh |
| [Guidi & Dominici 2026](032-guidi-dominici-2026-scope1-scope2-water-geography.md) | 3:1 | 472 facilities; 1.7:1 without hydro allocation |
| [CRS / IEA 2026](034-crs-2026-data-centers-water-faq.md) | 1.5:1 | 40% direct, 60% indirect |

The spread turns on whether reservoir evaporation is allocated to hydropower. Three independent
sources converge on 1.78 to 1.80 L/kWh for thermoelectric generation excluding hydro. The
convention can reverse regional rankings 94-fold: Oregon spans 0.30 to 28.18 L/kWh depending on
the choice.

## Scale depends on where it is measured

Direct data-centre water is about 2% of US consumptive use
([034](034-crs-2026-data-centers-water-faq.md)). Peak-day demand at individual sites spans 0.002
to 1.34 of the host utility's entire delivery capacity, the upper bound being Meta's Lebanon,
Indiana facility ([033](033-akinade-2026-water-consumption-impact-utility-burden.md)). Data
centres run consumptive ratios of 0.70 to 0.90 against a 12% public-supply average, with peaking
factors of 6 to 30 against 1.5 to 2.5.

Ceres reports 3.4 trillion gallons **withdrawn** across seven states in 2024, about 78% of it
hydropower pass-through, chosen as a risk-exposure proxy
([028](028-ceres-2026-water-behind-the-watts.md)). It is not comparable to municipal consumption.

## Efficiency estimates for non-hyperscale facilities

US small data centres held PUE flat at 1.82-2.28 between 2012 and 2018 while WUE fell from
0.26-0.42 to 0.21-0.35 L/kWh. Midsize facilities improved PUE from 1.46-1.83 to 1.43-1.76 while
WUE rose from 0.52-0.86 to 0.56-0.96 L/kWh, by adopting water-cooled chillers
([022](022-lei-2025-us-midsize-data-centers-wue.md)). Neither figure is measured: both weight
published per-cooling-system values by modelled county server counts.

Google's LLM-serving fleet WUE of 1.15 L/kWh sits above the midsize estimate, which cuts against
the assumption that non-hyperscale facilities are uniformly more water-intensive per unit of IT
energy.

## Gaps

- No independent verification of Google's 0.26 mL beyond reconstruction from Google's own inputs.
- No independent assessment of water-positive pledge delivery. Corporate self-report only.
- Meta has published no FY2025 water data; its latest covers calendar 2024.
- Privette, Barros & Cai (*AGU Advances* 2026) is directly on this topic and unretrieved.
