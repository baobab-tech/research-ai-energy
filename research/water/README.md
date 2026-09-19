# Water

35 excerpts on data-centre water: cooling technology, per-query estimates, the on-site and
off-site boundary, corporate disclosure, and site-level constraint.

[Full index](_index.md)

## The per-query estimates, reconciled

Google reports 0.26 mL per median Gemini text prompt. Li et al. estimated 10 to 25 mL per
ChatGPT query. [Sharma et al. 2026](027-sharma-2026-water-cost-of-intelligence-boundary.md)
reconstruct Google's figure to within 2.3% from Google's own published inputs and identify what
each number covers:

| Figure | Value | Boundary |
|---|---|---|
| Google, as reported | 0.26 mL | on-site cooling, WUE Category 2 under ISO/IEC 30134-9 |
| Same prompt, full boundary | 0.725 mL | adding generation water at 1.80 L/kWh, +179% |
| Long prompt (9.2 Wh), full boundary | 28 mL | inside Li et al.'s range |

Boundary accounts for about 2.8x of the difference. Prompt length accounts for the rest. Google
reports the median. The two estimates measure different quantities.

Google's 2026 report derives its water figure by applying its 2024 fleetwide WUE to a May 2025
energy measurement, and publishes no WUE figure anywhere in the document
([031](031-google-2026-fy2025-water-disclosure.md)).

## Withdrawal against consumption

Conflating these two is the most common error in this literature.

- **Withdrawal** is water taken from a source. It may return to the basin.
- **Consumption** is water evaporated or otherwise removed from the basin.

The Ceres headline of 3.4 trillion gallons for seven states in 2024 is a **withdrawal** figure,
about 78% of it hydropower pass-through, chosen deliberately as a risk-exposure proxy
([028](028-ceres-2026-water-behind-the-watts.md)). It is not comparable to municipal consumption.

## The indirect multiplier is unsettled

Off-site water consumed generating data-centre electricity, against on-site cooling water:

| Source | Ratio | Note |
|---|---|---|
| [LBNL 2024](029-shehabi-2024-lbnl-direct-vs-indirect-water.md) | 12:1 | 66 GL direct, ~800 GL indirect, 4.52 L/kWh |
| [Guidi & Dominici 2026](032-guidi-dominici-2026-scope1-scope2-water-geography.md) | 3:1 | 472 facilities; falls to 1.7:1 without hydro allocation |
| [CRS / IEA 2026](034-crs-2026-data-centers-water-faq.md) | 1.5:1 | 40% direct, 60% indirect |

The spread turns on one convention: whether reservoir evaporation is allocated to hydropower.
Three independent sources converge on 1.78 to 1.80 L/kWh for thermoelectric generation excluding
hydro. The convention can reverse regional rankings 94-fold, with Oregon spanning 0.30 to
28.18 L/kWh depending on the choice.

## Scale depends on where it is measured

Direct data-centre water is about 2% of US consumptive use
([034](034-crs-2026-data-centers-water-faq.md)). Peak-day demand at individual sites spans 0.002
to 1.34 of the host utility's entire delivery capacity, the upper bound being Meta's Lebanon,
Indiana facility ([033](033-akinade-2026-water-consumption-impact-utility-burden.md)). Data
centres run consumptive ratios of 0.70 to 0.90 against a 12% public-supply average, with peaking
factors of 6 to 30 against 1.5 to 2.5.

## Pledge accounting

Microsoft reports 8,170 ML consumed in FY25, up 22%, against 14.2 million m³ replenished, giving
"water positive" as a global aggregate. Its first site-level table shows 7 of 28 locations have
delivered replenishment, concentrated where withdrawal is small, while Boydton, Ashburn, Chicago
and Dublin have none ([030](030-microsoft-2026-fy25-site-level-water.md)). Google's 78% figure
uses a freshwater-only denominator; against total consumption it is 71%
([031](031-google-2026-fy2025-water-disclosure.md)).

## Gaps

- No independent verification of Google's 0.26 mL beyond reconstruction from Google's own inputs.
- No independent assessment of water-positive pledge delivery. Corporate self-report only.
- Meta has published no FY2025 water data; its latest covers calendar 2024.
- Privette, Barros & Cai (*AGU Advances* 2026) is directly on this topic and unretrieved. Wiley
  blocks automated access.
