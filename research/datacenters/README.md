# Data Centres

17 excerpts, every one verified against its source, on infrastructure: buildout and interconnection, power sourcing, cooling, and
efficiency metrics.

[Full index](_index.md)

## Announced capacity against energised capacity

The chain runs: requested, studied, agreement signed, under construction, energised. Attrition is
severe at each step and sources report the stages interchangeably.

ERCOT holds about 474 GW of large-load interconnection requests, roughly 90% of it data centres
and about five times the entire ERCOT system peak. Only ~205 GW passed the first SB 6 eligibility
screen; 274 GW across 315 projects had no qualifying study
([017](017-ercot-2026-large-load-queue-474gw.md)). Fewer than one in five proposed US power
projects reaches operation ([021](021-granderson-2026-dc-demand-flexibility-tariffs.md)).

LBNL converts its 2030 electricity projection to 148 GW of interconnection capacity by assuming
50% interconnection utilisation, an assumption the authors state is "not well documented." That
single figure drives the GW result linearly ([016](016-lbnl-2026-us-dc-energy-2025-update.md)).

Climate siting moves PUE by about 1.23x across ASHRAE zones, from 1.16 to 1.43 in a 10 MW
air-cooled model ([004](004-kim-2024-data-center-pue-economizers.md)). That model is validated
against another model, not against metered data, and one co-author is employed by a data-centre
construction firm that also funded the work.

## Metered figures

Ireland publishes the only national metered series: data centres took 23% of all metered
electricity in 2025, 7,663 GWh and up 10% year on year, against 28% for all housing
([019](019-cso-2026-ireland-datacentres-23-percent.md)).

PJM reports energy demand growing 5.3% a year against a 3.6% summer peak, the flat-profile
signature of data-centre load, with 13 zones manually adjusted because the models could not fit
them ([022](022-pjm-2026-load-forecast-energy-outpaces-peak.md)).

## Nuclear: contracted against delivering

Up to 13 GW of hyperscaler nuclear has been announced and 0 GW of it is operating. The earliest,
Crane (formerly Three Mile Island) at 835 MW, targets 2027. Palisades, an intact plant and the
easiest case, missed a February 2026 restart and had delivered no electrons as of July 2026 with
about 5,000 work items open. Meta's Clinton agreement buys clean-energy credits while the power
continues to the regional market ([020](020-carnegie-2026-hyperscaler-nuclear-13gw-zero-operating.md)).

## PUE understates AI-side waste

PUE measures facility overhead against IT load. It is blind to energy wasted inside the IT load
itself. LBNL's own High Inference Energy scenario adds 20.6% to national electricity through
idle power and low utilisation while leaving PUE unchanged
([016](016-lbnl-2026-us-dc-energy-2025-update.md)). Fleet PUE falls from 1.45 to 1.36 by 2030
through mix shift toward liquid-cooled sites.

Published averages diverge by source and by method:

| Figure | Population | Method |
|---|---|---|
| 1.09 to 1.4 | hyperscaler self-reported | operator disclosure |
| 1.36 weighted | 681 EU facilities ([policy/020](../policy/020-dg-ener-2025-first-eu-data-centre-reporting-round.md)) | mandatory reporting |
| 1.45 US fleet, 1.145 AI-serving | national ([016](016-lbnl-2026-us-dc-energy-2025-update.md)) | modelled from stock |
| 1.82 to 2.28 small, 1.43 to 1.76 midsize | US non-hyperscale ([012](012-lei-2025-us-small-midsize-dc-cbecs.md)) | survey-weighted estimate |
| 2.23 | six undated published breakdowns ([015](015-setyo-2025-dc-energy-efficiency-thermal-review.md)) | inverse of the mean IT share |

The 2.23 is the reciprocal of an unweighted mean of six IT-share figures (1 / 0.448), four of
them illustrative diagrams, with no facility type, size or year attached. Lei's 1.82 to 2.28 band
for small facilities is the defensible non-hyperscale comparator. PUE's originator has endorsed
replacing the metric ([023](023-verrus-2026-pue-critique-pux.md)).

## Off-grid proposals

Modelled off-grid hybrid systems beat the grid on cost and emissions for a 50 MW flat load
([013](013-rollinson-2025-offgrid-hyperscale-feasibility.md)), on three conditions worth stating:
every site carries 50 MW of gas supplying 8 to 19.6% of annual energy, costs are compared against
2023 peak retail industrial prices, and grid carbon intensity is held flat at its 2023 annual
average for 35 years. The largest off-grid AI campus actually built chose about 1.2 GW of
unabated gas, and its binding constraint was air permitting
([025](025-selc-earthjustice-2026-xai-memphis-unpermitted-turbines.md)).

## Counter-evidence on overbuild

CBRE reports 1.4% vacancy and 80.4% of 7,481 MW under construction preleased, with Northern
Virginia at 0.2% ([024](024-cbre-2026-vacancy-1-4-percent-preleasing.md)). The absorption data
does not support a physical-overbuild thesis. CBRE is a broker, and the data excludes hyperscaler
self-build, which is where overbuild risk concentrates. Queue inflation and physical overbuild
are separate phenomena.

## Gaps

- **GW actually energised per year is published by no source.** The largest hole in this folder.
- Accelerator depreciation schedules from primary filings. Commentary only.
- 24/7 carbon-free energy progress reporting for 2026.
- Whether any hyperscaler has signed a mandatory-curtailment tariff.
