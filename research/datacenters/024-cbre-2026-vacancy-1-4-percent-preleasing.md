# North American data-centre vacancy is 1.4% and 80% of capacity under construction is already leased — the market data contradicts the overbuild thesis, for now

**Topic:** Data-centre infrastructure — buildout, absorption, overbuild and stranded-capacity risk
**Source:** CBRE, *North America Data Center Trends H1 2026*
**Type:** commercial market report
**URL:** https://www.cbre.com/insights/books/north-america-data-center-trends-h1-2026
**Source note:** content retrieved 2026-09-19; the URL returns HTTP 403 to plain automated requests but serves in a browser
**Published:** 2026-08-27

## Finding

If AI data-centre capacity were being overbuilt, it would show as rising vacancy and falling preleasing. It shows the opposite. Primary-market vacancy fell to 1.4% from 1.6% a year earlier, and 80.4% of the 7,481 MW under construction is already preleased, up from 74.3%. Northern Virginia, the largest market at 4,497 MW, has a 0.2% vacancy rate. Under 1,500 MW is available across all primary markets against 10,903 MW of inventory. The constraint CBRE identifies is not demand but delivery: "power availability and infrastructure delivery timelines remain the most decisive factors," with energisation delays from permitting, planning and zoning on last-mile projects.

This is the counterweight to the 2025 lease-cancellation reporting (TD Cowen on Microsoft) that seeded the overbuild narrative. Cancelled leases at one hyperscaler coexisted with an absorption market that has tightened, not loosened. Stranded-capacity risk in this dataset sits in the future — in whether the 7.5 GW under construction energises on schedule and whether preleases signed at today's prices are honoured — not in vacant space today.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Primary-market inventory | 10,903 MW (+33.7% YoY) | North America primary markets |
| Under construction | 7,481.1 MW (+24.8% vs H1 2025) | |
| Preleased share of under-construction | 80.4% (vs 74.3% prior year) | |
| Vacancy rate | 1.4% (vs 1.6% H1 2025) | |
| Net absorption | 1,456.2 MW (+11.7% YoY) | |
| Available capacity, all primary markets | <1,500 MW | |
| Northern Virginia inventory | 4,496.5 MW | Largest market |
| Northern Virginia vacancy | 0.2% | |
| Northern Virginia under construction | 2,420.2 MW (+16.5%) | |
| Northern Virginia net absorption | 467.6 MW | Led all primary markets |

## Methodology

CBRE tracks leased and available megawatts of commissioned IT capacity across defined primary markets from its own brokerage and market-tracking data. Units are MW of IT capacity, not GW of grid interconnection, and the two are not interchangeable — LBNL estimates interconnection capacity runs at roughly 50% utilisation, so 10.9 GW of leased IT capacity implies materially more contracted grid capacity.

## Limitations and conflicts

CBRE is a commercial real-estate brokerage with revenue tied to data-centre transaction volume and a direct interest in a tight, rising market. The methodology is proprietary and the market definitions are CBRE's own. The dataset covers third-party colocation and wholesale leasing; hyperscaler self-build — where most AI training capacity sits — is largely outside it, which is precisely where overbuild risk would concentrate. "Preleased" is a signed commitment, not delivered revenue, and says nothing about whether those leases survive a demand reversal. Vacancy near zero is also consistent with a supply shortage caused by power-delivery failure rather than with healthy demand; CBRE's own energisation-delay commentary supports that reading.

Unresolved: this source does not report cancelled or deferred projects. A complete overbuild-risk picture also needs accelerator depreciation schedules (hyperscalers extended assumed useful life to five to six years, which lowers reported cost per unit of compute and would understate impairment if accelerators retire sooner) — not established here and flagged as a gap.

## Relation to existing corpus

No direct overlap — the folder had no market or capital-market material. Constrains `017-ercot-2026-large-load-queue-474gw.md`: speculative interconnection requests are abundant, but built colocation capacity is absorbed on delivery, so queue inflation and physical overbuild are separate phenomena.

---
Retrieved: 2026-09-19
Search: Serper "data center vacancy cancelled leases 2026 Microsoft lease cancellations stranded capacity CBRE absorption"
