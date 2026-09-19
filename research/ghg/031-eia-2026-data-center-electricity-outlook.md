# EIA now models data-centre servers separately: ~7% of US commercial electricity in 2025, rising to 22-33% by 2050

**Topic:** GHG emissions — US federal statistical agency forecasts of data-centre electricity demand
**Source:** US Energy Information Administration — *Annual Energy Outlook 2026* (via Today in Energy) and *September 2026 Short-Term Energy Outlook*, 2026
**Type:** agency report / dataset
**URL:** https://www.eia.gov/todayinenergy/detail.php?id=67704
**Source note:** and https://www.eia.gov/pressroom/releases/press592.php
**Published:** 2026-05-19 (AEO analysis); 2026-09-09 (STEO)

## Finding

EIA changed its model rather than only its numbers: for AEO2026 it "updated the Commercial Demand Model to report data center server electricity use separately from the broader category of commercial computing," so US data-centre load now has a dedicated line in the federal energy forecast for the first time. Servers are about 7% of commercial-sector electricity in 2025 and reach 22-33% by 2050, or 446-818 BkWh from servers alone. In the near term, the September 2026 STEO has US electricity sales reaching a record 4,135 BkWh in 2026 (+~2%) and 4,211 BkWh in 2027, with commercial-sector sales growing 3.3% and 2.7% — the commercial sector alone accounting for 63% and 56% of total sales growth in those years, driven by data centres.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Server share of commercial electricity, 2025 | ~7% | AEO2026 model output |
| Server share, 2050 | 22-33% | Counterfactual Baseline to High Electricity Demand cases |
| Server electricity, 2050 | 446-818 BkWh | Servers only, excludes cooling |
| Standalone data centres, 2050 | 581 BkWh | High Electricity Demand case |
| Commercial electricity intensity | Exceeds the 2003 record of 14.9 kWh/sq ft in 2031-2032 | |
| Cooling intensity multiplier | 2.9x more energy-intensive than non-data-centre space | Modelled |
| Server load shape | Essentially flat hourly | Modelling assumption |
| US electricity sales 2026 / 2027 | 4,135 / 4,211 BkWh | STEO Sep 2026; +~2% each year |
| US generation 2026 / 2027 | 4,368 BkWh (+2.2%) / +1.7% | Record |
| Commercial sales growth 2026 / 2027 | +3.3% / +2.7% | 63% / 56% of total sales growth |
| Regional concentration | West South Central largest contributor, despite a pause in new Texas projects | |

## Methodology

Historical baselines come from the Commercial Buildings Energy Consumption Survey (CBECS), notably 2003 — survey data, more than two decades old for the intensity benchmark. Everything from 2025 onward is model output under two bracketing cases (Counterfactual Baseline and High Electricity Demand), not a forecast with a central estimate. The flat-load-shape assumption for servers is a modelling convenience that matters for capacity planning conclusions. The STEO is a short-horizon forecast revised monthly; EIA cut its 2026 generation forecast by more than a percentage point relative to earlier 2026 editions.

## Limitations and conflicts

EIA is a US federal statistical agency with no commercial interest, but its data-centre representation is new and untested, and CBECS-based historical anchors substantially predate the AI buildout. The AEO2026 figures are server electricity, excluding facility cooling and power overhead, so they are not comparable with LBNL's facility-level TWh (025) without adding PUE. EIA publishes electricity, not emissions. The 2050 horizon carries no meaningful confidence: a 22-33% range at 25 years out reflects scenario design, not estimated uncertainty. The STEO attributes growth to data centres qualitatively without quantifying the data-centre contribution separately.

## Relation to existing corpus

No direct overlap — EIA appeared nowhere in `research/` before this file. Provides the official US federal counterpart to the LBNL bottom-up estimate (025) and a near-term demand check on the IEA projections (023, 024).

---
Retrieved: 2026-09-19
Search: WebSearch "EIA Short-Term Energy Outlook September 2026 data centers"; WebFetch eia.gov Today in Energy 67704 and press592
