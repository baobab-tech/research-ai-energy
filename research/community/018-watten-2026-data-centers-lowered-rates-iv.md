# An EPRI instrumental-variables study finds data-centre growth caused US residential rates to fall ~0.4% per 10% capacity increase, 2015-2024

**Topic:** Electricity prices — the strongest published counter-argument to the ratepayer-harm thesis, and the conditions under which it stops holding
**Source:** Asa Watten (EPRI), John Bistline (Watershed), Geoffrey Blanford (EPRI), 2026
**Type:** preprint (arXiv, physics.soc-ph)
**URL:** https://arxiv.org/abs/2606.19777
**Published:** 2026-06-18

## Finding

Using state-level panel data and an instrument based on the 1947 Eisenhower Interstate Highway Plan, the authors estimate that a 10 percent increase in data-centre capacity caused average residential retail rates to fall by about 0.4 percent. Scaled up: the average residential customer over 2019-2024 lived in a state where data-centre capacity grew 160 percent, which the model attributes to a 6 percent rate *decrease*. The mechanism they propose is that retail tariffs recover average, not marginal, cost — new durable load spreads large embedded fixed costs over more kWh, and new generation capacity has a lower levelized cost than the incumbent asset mix. They state three conditions under which the sign flips, and two of them are already present.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Elasticity, residential retail price to data-centre capacity | -0.04 (a 10% capacity rise → 0.4% price fall) | State-level IV, 2015-2024, inverse hyperbolic sine of capacity |
| Implied cumulative effect 2019-2024 | -6% for the average residential customer | Mean customer-weighted capacity growth of 160% |
| First-stage F statistic | 7.8 (preferred specification) | Below the conventional weak-instrument threshold of 10 |
| Inference | Anderson-Rubin test significant at 0.1%, rejecting positive effects | Weak-instrument-robust |
| Commercial and industrial price effects | Same sign, smaller magnitude | Supplemental appendix |
| Cross-state spillover elasticity | 0.007, not significant, instrument "quite weak" | |
| US data-centre share of electricity, 2024 | 4.5%, projected 9-17% by 2030 | EPRI 2026a; excludes cryptocurrency mining and hosting |
| Reported 2021-2024 baseline | Demand +1.5%/yr, rates +5.2%/yr vs core CPI +5.8%/yr | EIA; real rates roughly flat |

## Methodology

Two-stage least squares on a state-year panel. The identifying assumption is that the length of the 1947 interstate highway plan within a state predicts present-day data-centre siting (fibre corridors follow old highway rights of way) but is otherwise unrelated to electricity price changes conditional on GDP and population. The authors are explicit that OLS is confounded in an unknown direction and that the IV is needed to adjudicate. Supporting descriptive evidence: transmission and distribution capex and opex, and generation capex and opex, all fall per unit delivered as demand rises.

The estimate is an *average* effect over a period ending in 2024. It is not a forecast, and the paper is careful about this: "We caution that future supply constraints could reverse the effect."

## Limitations and conflicts

Two of three authors are EPRI employees; EPRI is funded by the electric utility industry, which is the party arguing that data-centre load does not harm ratepayers and which earns a regulated return on the capital expenditure this load induces. The third author is at Watershed, a carbon-accounting firm. This does not make the econometrics wrong, but the result is exactly the one the funder would want, and the paper's framing ("Despite prevailing sentiment") is advocacy-adjacent.

A first-stage F of 7.8 is weak by convention; the authors handle this with Anderson-Rubin inference rather than by finding a stronger instrument. The exclusion restriction is arguable — 1947 highway planning correlated with industrial geography, which plausibly affects electricity cost structures through channels other than data centres.

The authors' own caveats do most of the damage to any forward-looking use of the result. They note gas-turbine order backlogs bidding up prices, transformer supply-chain constraints, solar tariffs, and stalled federal wind and solar approvals — each of which makes incremental capacity more expensive than incumbent supply, which is the precise condition that reverses the sign. They also note that if announced load exceeds realised consumption, fixed costs spread across fewer kWh and the mechanism inverts. The study period (2015-2024) ends before the PJM capacity price spikes of 2025-2026.

## Relation to existing corpus

Directly contradicts, on a different measure and period, the cost attribution in /Users/olivier/DEV/research-ai-energy/research/community/016-monitoring-analytics-2026-pjm-capacity-data-center.md. The two are reconcilable: PJM's monitor measures the capacity-market component in one RTO in 2025-2027 under binding scarcity, while this paper measures all-in average retail rates nationally through 2024 when capacity was slack. The disagreement is about whether the system is supply-constrained, which is the paper's own stated switch. No overlap with files 001-015.

---
Retrieved: 2026-09-19
Search: WebSearch "data centers electricity bills econometric study 2026 retail rates causal estimate counties peer reviewed" -> arXiv 2606.19777 full PDF
