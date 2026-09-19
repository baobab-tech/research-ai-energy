# PJM's market monitor attributes $23.1 billion of capacity-auction cost increases across three delivery years to data-centre load

**Topic:** Grid impact / electricity prices — does data-centre load raise costs borne by other ratepayers, and by what mechanism
**Source:** Monitoring Analytics, LLC (the Independent Market Monitor for PJM), 2026
**Type:** regulatory / market-monitor report
**URL:** https://www.monitoringanalytics.com/reports/Reports/2026/IMM_Analysis_of_the_20272028_RPM_Base_Residual_Auction_Part_A_20260105.pdf
**Published:** 2026-01-05

## Finding

PJM's independent market monitor re-ran the 2027/2028 Base Residual Auction (held 4-10 December 2025) with data-centre load removed from the peak load forecast. Total auction revenues fell from $16.41 billion to $9.91 billion, so the presence of 17,071 MW of existing and forecast data-centre load raised auction revenues by $6.50 billion, or 65.5 percent. Summing the equivalent counterfactuals for the three most recent auctions gives $23.10 billion. Those revenues are recovered from load-serving entities and flow into retail bills. The monitor states the conclusion without hedging: "data center load growth is the primary reason for recent and expected capacity market conditions, including total forecast load growth, the tight supply and demand balance, the significant shortfall in cleared capacity, and high prices."

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| 2027/2028 BRA total RPM revenues (actual) | $16,411,578,225 | Scenario 0: actual clearing prices x cleared MW + uplift MW |
| Revenues with all data-centre load removed | $9,913,924,713 | Scenario 4: 17,071 MW (embedded + above-embedded) removed from 2027 peak load forecast |
| Increase attributable to data-centre load, 2027/28 | $6,497,653,512 (+65.5%) | Scenario 0 minus Scenario 4 |
| Increase attributable to forecast (not yet built) data-centre load only | $6,244,523,827 (+61.4%) | Scenario 3: 13,018 MW of new + growth-in-existing load removed |
| 2025/2026 BRA increase | $7,742,960,157 (above-embedded) / $9,332,103,858 (all DC load) | Scenario 88 of the 2025/2026 Part G report |
| 2026/2027 BRA increase | $7,271,197,971 | Scenario 4 of the 2026/2027 Part A report |
| Three-auction total | $23,100,955,341 | Sum of "all data center load" column, Table 1 |
| Data-centre load in 2025 PJM load forecast for DY 2027/28 | 17,071 MW total; 13,018 MW new/forecast growth; 4,053 MW existing | PJM 2025 Load Forecast Report |
| 2027/2028 capacity shortfall vs reliability requirement | 6,516.6 MW UCAP (5.6% below the IRM in ICAP terms) | PJM auction report, corrected 5 Jan 2026 |
| Same counterfactual under an unrestricted VRR curve | +$19,447,850,870 (+282.8%) | Scenario 6: removes the Shapiro-PJM price cap/floor agreement |

## Methodology

Counterfactual auction re-clearing, not regression. The monitor re-runs the actual auction supply curve against a demand curve built from a peak load forecast with the data-centre component subtracted, holding supply offers, the VRR curve shape and all other parameters constant. This isolates the price effect of the demand shift but assumes supply would have been identical without data-centre expectations — the report itself concedes that point implicitly by noting PJM "would have eventually reached a point where supply and demand were tight, but that trajectory was relatively slow."

The 2027/2028 auction used a price cap of $333.44/MW-day and a floor, both products of a settlement between Governor Shapiro of Pennsylvania and PJM (FERC Docket ER25-1357). The floor mechanically shrinks the measured data-centre effect, because without data-centre load the auction would have cleared below the floor; the monitor puts that suppression at $3,036,924,737. The cap suppresses the actual price. Both distortions run in opposite directions from the usual assumption, so the $6.5 billion figure is conservative relative to an unconstrained market.

## Limitations and conflicts

Monitoring Analytics is PJM's FERC-mandated independent market monitor, funded through PJM but structurally separate and frequently adversarial toward PJM; it has an explicit policy position (it recommends requiring new data-centre load to bring its own generation) that the analysis supports. PJM disputes the framing that the capacity market is anything other than supply and demand; the monitor rebuts this directly: "It is misleading to assert that the capacity market results are simply just a reflection of supply and demand."

The measured quantity is capacity-market revenue, not retail bills. Capacity is a minority component of a retail bill, and load hedged through self-supply or bilateral contracts is not exposed to clearing prices — so the $23.1 billion does not translate one-for-one into consumer cost. Crucially, the largest single input is a *forecast*: 13,018 of the 17,071 MW is load that does not yet exist. If announced data centres do not materialise, ratepayers will have paid for capacity procured against phantom demand, which is the stranded-cost exposure in a different guise.

## Relation to existing corpus

No direct overlap. The community folder contained no PJM, capacity-market or wholesale-price material; files 005 and 009 discuss the 2022 European energy crisis and household energy poverty in general terms, not data-centre cost allocation. This is the first documented causal-mechanism evidence in the folder.

---
Retrieved: 2026-09-19
Search: WebSearch "PJM capacity auction 2026 results data center load electricity price increase ratepayers" -> Utility Dive -> primary IMM report PDF
