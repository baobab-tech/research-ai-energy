# PUE's originator endorses replacing it: a vendor framework shows conventional designs convert 49% of utility energy into productive IT load while reporting good PUE

**Topic:** Data-centre infrastructure — efficiency metrics, what PUE excludes
**Source:** Verrus, *Beyond PUE: Rethinking Efficient Data Center Design in an Era of Power Scarcity*, 2026
**Type:** corporate disclosure (vendor white paper — treat as an interested party's methodology proposal)
**URL:** https://verrusdata.com/news/beyond-pue
**Published:** 2026-01-15

## Finding

The argument is that PUE measures infrastructure overhead but says nothing about how much of the energy a site is actually entitled to draw ends up doing computation. Verrus proposes a three-part "PUx" framework adding Provisioned Utility Capacity (share of contracted utility energy allocatable to SLA-backed IT nameplate) and Productive Utilization of Nameplate (share of reserved IT power actually consumed by productive load) alongside PUE. In their modelled case study a conventional design converts 49% of total utility energy into productive IT load; their own 70 MW design reaches ~75%, a 53% improvement, freeing 18 MW of compute within the same interconnection. Christian Belady, who originated PUE, is a Verrus advisor and endorsed the framework.

The structural point stands independently of the vendor: PUE is a ratio with IT load in the denominator, so every watt wasted *inside* the IT envelope — idle accelerators, over-provisioned nameplate reservations, unutilised interconnection headroom — either does not affect PUE or improves it. AI workloads concentrate waste precisely there. LBNL's own model (see 016) demonstrates the same effect from the other direction: its High Inference Energy scenario raises US data-centre electricity by 20.6% purely through higher idle power and utilisation of IT equipment, and leaves PUE unchanged.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Conventional design: utility energy → productive IT load | 49% | Verrus modelled case study |
| Verrus 70 MW design | ~75% | 53% relative improvement |
| Additional compute unlocked within same interconnection | 18 MW | |
| Claimed annual value | ~$35M | At $145/kW/month lease rate |
| Provisioned Utility Capacity (PUC), case study | 77% | Share of utility energy allocatable to SLA-backed IT nameplate |
| Productive Utilization of Nameplate (PUN), case study | 96% | Share of reserved IT power actually consumed by productive load |
| Typical interconnection capacity utilisation, industry | ~50% | Per LBNL 2026, citing redundancy and maintenance requirements |

## Methodology

A modelled case study of a single 70 MW facility design against an unspecified "conventional" baseline. The metric definitions are the substantive contribution; the numbers are design-stage modelling, not measurement of operating facilities.

## Limitations and conflicts

Verrus is a data-centre developer selling the design the framework scores well. The baseline it is compared against is not specified, the modelling is not published in auditable form, and the headline $35M figure is a revenue calculation for the operator, not an energy or emissions result. Belady's endorsement is not independent — he is a Verrus advisor. A metric proposed and computed by the party being measured carries the same problem PUE itself acquired once it became a marketing number. Cite this for the *critique* and the metric definitions; do not cite the 49%/75% comparison as an industry finding.

The corroboration that does not come from Verrus: LBNL's 2026 report independently states that interconnection-capacity utilisation "is not well documented but is estimated to be around 50% due to high redundancy requirements and maintenance needs," and cites Verrus (2026) for the industry effort to raise it. At 50% utilisation, half of every megawatt a data centre reserves from the grid — capacity that forecloses other interconnection applicants and drives transmission build — does no work, and PUE is silent on all of it.

## Relation to existing corpus

Supplies the 2026 metric critique the folder lacked. Reframes `004-kim-2024-data-center-pue-economizers.md` (PUE 1.15–1.43 by climate and cooling) and `015-setyo-2025-dc-energy-efficiency-thermal-review.md` (average PUE 2.23): both dispute PUE *values* while accepting PUE as the measure. This source disputes the measure.

---
Retrieved: 2026-09-19
Search: Serper "Verrus Beyond PUE 2026 rethinking efficient data center design power scarcity"
