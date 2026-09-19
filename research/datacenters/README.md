# Data Centres

25 excerpts on infrastructure: buildout and interconnection, power sourcing, cooling, and
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

Reported averages diverge widely by source: 2.23 in one review of the general population
([015](015-setyo-2025-dc-energy-efficiency-thermal-review.md)) against hyperscaler claims of 1.1
to 1.4, and 1.36 weighted in the first mandatory EU reporting round
([policy/020](../policy/020-dg-ener-2025-first-eu-data-centre-reporting-round.md)). PUE's
originator has endorsed replacing it ([023](023-verrus-2026-pue-critique-pux.md)).

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
