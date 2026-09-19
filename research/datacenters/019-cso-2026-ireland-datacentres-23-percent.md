# Irish data centres consumed 23% of all metered electricity in 2025 — the only national figure that is metered rather than modelled

**Topic:** Data-centre infrastructure — regional saturation, Ireland
**Source:** Central Statistics Office (Ireland), *Data Centres Metered Electricity Consumption 2025*
**Type:** official statistics (national statistical institute)
**URL:** https://www.cso.ie/en/releasesandpublications/ep/p-dcmec/datacentresmeteredelectricityconsumption2025/keyfindings/
**Published:** 2026-07-07

## Finding

Ireland's national statistical office reports data-centre metered electricity at 7,663 GWh in 2025, 23% of all metered electricity in the state, up from 5% in 2015. Data centres now consume more electricity than all urban dwellings (18%) and are within five percentage points of all residential consumption combined (28%). Growth was 10% year-on-year while all other users grew 2%. This matters beyond Ireland because almost every other national data-centre figure in circulation — including the IEA's and LBNL's — is modelled from equipment shipments or sampled surveys. Ireland's is derived from meter readings on the distribution network, so it is the closest thing to a ground-truth national observation available, and it lands far above the modelled global average share of ~1.5%.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Data-centre metered electricity, 2025 | 7,663 GWh | Metered; identified customer accounts |
| 2024 | 6,973 GWh | |
| Year-on-year growth | +10% | Against +2% for all other users |
| Share of total metered electricity, 2025 | 23% | Up from 5% in 2015 |
| Urban residential share | 18% | |
| Rural residential share | 9% | |
| All residential | 28% | |
| Q1 2015 | 291 GWh | |
| Q4 2025 | 1,991 GWh | +584% over the period |

## Methodology

CSO takes metered consumption records from the electricity network and attributes them to data centres, because "data centres are not separately classified in the source data." Identification uses name searches for known data-centre operators, industry reports, internet searches, and examination of high-consumption customers. The series is quarterly from Q1 2015.

## Limitations and conflicts

No funding conflict — a national statistical institute publishing under official statistics obligations. The methodological weakness is attribution, not measurement: because data centres have no separate classification code, the population is assembled by operator-name matching and a high-consumption threshold. That will miss data-centre load inside mixed-use or colocation accounts and may capture non-data-centre load at large industrial sites. The direction of the bias is not stated. The figure covers *metered* electricity only, so any behind-the-meter on-site generation — which Irish operators have been building in response to connection constraints — is excluded from both numerator and denominator, meaning the true data-centre share of electricity *consumed* is likely higher than 23%. Ireland is a small, highly concentrated market (most capacity in the Dublin region) and its share is not generalisable; it is useful as an existence proof of what saturation looks like, not as a forecast for other jurisdictions.

## Relation to existing corpus

No direct overlap. Complements `011-commins-2025-eu-dc-sustainability-policy.md` on EU policy with the Irish outcome that policy is reacting to. Provides a measured counterpoint to the modelled national figures in `016-lbnl-2026-us-dc-energy-2025-update.md` and `018-iea-2026-global-dc-electricity-us-share.md`.

---
Retrieved: 2026-09-19
Search: WebSearch "CSO Ireland data centres metered electricity consumption 2025 2026 official statistics share"
