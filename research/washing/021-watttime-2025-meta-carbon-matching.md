# Consequential accounting puts Meta's 2023 data centre net emissions at 770,000 tonnes against 733 tonnes reported under GHGP

**Topic:** Greenwashing evidence — additionality of clean energy procurement; annual vs hourly vs emissions matching
**Source:** WattTime, "How carbon accounting approaches do (or don't) reveal real-world impacts: An analysis of three methodologies to report emissions from Meta's 2023 data center electricity consumption and clean energy procurement"
**Type:** NGO technical report
**URL:** https://watttime.org/wp-content/uploads/2025/06/WattTime-Meta-Emissions-Accounting-Case-Study-vFinal-202505b.pdf
**Published:** 2025-05

## Finding

WattTime recalculated Meta's 2023 data centre electricity emissions three ways. Under the current GHGP market-based method (annual matching) Meta reports 733 tonnes CO2e, down from roughly 5 million tonnes unabated. Under "carbon matching" — time- and location-specific induced emissions minus time- and location-specific avoided emissions from Meta's own procurement — Meta's consumption induced 8.12 million tonnes and its clean energy avoided about 7.35 million tonnes, leaving 770,000 tonnes net. The consequential estimate is roughly 1,050x the reported figure. The same analysis found Meta's procurement genuinely did offset about 90% of induced emissions, so the finding cuts both ways: the reported number is wrong by three orders of magnitude, but Meta's underlying clean-energy programme is substantively effective.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Reported electricity emissions, annual matching | 733 tonnes CO2e | GHGP market-based, 2023 data centres |
| Unabated electricity emissions | ~5,000,000 tonnes CO2e | before procurement, annual matching basis |
| Induced emissions, carbon matching | 8,120,000 tonnes CO2e | hourly, location-specific marginal emissions rates |
| Avoided emissions, carbon matching | ~7,350,000 tonnes CO2e | displacement attributable to Meta's own procurement |
| Net emissions, carbon matching | 770,000 tonnes CO2e | induced minus avoided |
| Ratio, carbon matching to reported | ~1,050x | 770,000 ÷ 733 |
| Portfolio-wide hourly CFE score | 79% | share of hours with matched clean supply in-region |
| PACW (Oregon) CFE score / avoided | 72% / 108,000 tonnes | grid already 69% clean before Meta acted |
| MISO (Midwest) CFE score / avoided | 92% / ~1,200,000 tonnes | grid 34% clean before Meta acted |
| Share of S&P 500 disclosers using annual matching, 2023 | 97% | WattTime citation |

## Methodology

Three methodologies applied to the same physical 2023 consumption and procurement. Annual matching is the current GHGP market-based method: annual MWh consumed minus annual MWh of clean electricity procured, residual multiplied by a grid residual emission factor. Hourly matching (24/7 CFE) measures the share of hours in which clean supply in the same balancing area matched consumption; WattTime states explicitly that this is not a carbon measurement and cannot be compared against the two carbon calculations. Carbon matching uses hourly nodal marginal emissions rates to compute induced emissions and the emissions displaced by Meta's procurement at the specific time and place it generated.

The PACW/MISO comparison is the report's sharpest result: two regions where Meta's data centres induced similar emissions (~700,000-800,000 tonnes each) and Meta scored 72% and 92% on hourly CFE, yet real avoided emissions differed by more than 10x because one grid was already 69% clean. Neither annual nor hourly matching distinguishes these cases.

## Limitations and conflicts

WattTime is a nonprofit that develops and sells marginal-emissions data and has an institutional interest in the GHG Protocol adopting emissions-matching methods; carbon matching is its own proposed methodology. The case study was produced as an input to the GHGP revision. Marginal emissions rates are modelled, not measured, and attributing displacement to a specific generator carries counterfactual uncertainty not quantified in the excerpt above. WattTime states the physical emissions impact of Meta's 2023 activity was identical under all three methods and that only the reported figure changes. The report is not adversarial toward Meta: its avoided-emissions estimate credits Meta's procurement with roughly 7.35 Mt of genuine reductions.

## Relation to existing corpus

No direct overlap. Supplies the consequential counterpart to the disclosed figures in `research/washing/020-meta-2025-scope2-4394x-gap.md`, and gives the folder a quantified answer to the additionality question rather than a theoretical one.

---
Retrieved: 2026-09-19
Search: Web search "Meta scope 2 location-based market-based"; PDF text extracted from the WattTime case study
