# The US share of world data-centre electricity is ~45%, not 40% — and the underlying numbers come from two different models that were never designed to be divided

**Topic:** Data-centre infrastructure — verifying the "US uses ~40% of world data-centre electricity" claim
**Source:** International Energy Agency, *Energy and AI* (2025), "Energy demand from AI"; numerator cross-checked against LBNL 2026
**Type:** agency report
**URL:** https://www.iea.org/reports/energy-and-ai/energy-demand-from-ai
**Published:** 2025-04 (IEA); US figure from LBNL, 2026-06-18

## Finding

The circulating claim (Forbes, R. Rapier, 2026-08-23, https://www.forbes.com/sites/rrapier/2026/08/23/the-us-now-uses-nearly-40-of-the-worlds-data-center-electricity/ — behind a block to automated retrieval, so the framing below is reconstructed from the datasets, not the article) rests on dividing a US data-centre figure by a global one. The global denominator traces to the IEA's *Energy and AI*: about 415 TWh in 2024, roughly 1.5% of global electricity. The best-documented US numerator for the same year is LBNL's 192 TWh (2026 update). That gives a US share of 46%, not "nearly 40%" — the claim is conservative rather than inflated. The IEA's own regional growth figures corroborate the magnitude independently: the US is projected to add around 240 TWh by 2030, a 130% increase, implying a 2024 US base of roughly 185 TWh, or 45% of the 415 TWh world total.

The qualification that matters is that the two numbers are not from one dataset. LBNL builds the US figure bottom-up from IT shipment data and explicitly excludes cryptocurrency mining; the IEA global figure uses its own scenario framework. Dividing one by the other is a defensible order-of-magnitude check, not a measured share, and no single dataset publishes both terms on a consistent boundary.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Global data-centre electricity, 2024 | ~415 TWh; ~1.5% of global electricity | IEA *Energy and AI*, scenario-based |
| Global, 2030 Base Case | ~945 TWh; just under 3% of global electricity | Doubling from 2024 |
| Global, 2035 Lift-Off Case | ~1,700 TWh (4.4% of global demand) | High AI-adoption sensitivity |
| Global, 2035 High Efficiency Case | ~970 TWh (2.6%) | |
| Global, 2035 Headwinds Case | ~700 TWh (<2%) | |
| US growth, 2024→2030 | +~240 TWh (+130%) | Implies ~185 TWh US base in 2024 |
| China growth, 2024→2030 | +~175 TWh (+170%) | Implies ~103 TWh base |
| Europe growth, 2024→2030 | +>45 TWh (+70%) | Implies ~64 TWh base |
| US + China share of global growth to 2030 | nearly 80% | |
| US 2024, LBNL bottom-up | 192 TWh | Excludes crypto mining |
| **Implied US share of world, 2024** | **45–46%** | 185–192 ÷ 415 |
| Implied US share, 2030 | ~45% | (185+240) ÷ 945 |

## Methodology

IEA uses a scenario-based approach with a Base Case plus three sensitivities (Lift-Off, High Efficiency, Headwinds) spanning uncertainty in efficiency gains and AI adoption rates. The report does not publish a headline "US share of world" percentage — the share must be constructed, which is why the figure varies between commentators. LBNL notes that the IEA's 2030 US projection (~430 TWh, published early 2025, methodology "broadly consistent" with LBNL's) sits substantially below LBNL's own 649 TWh Reference Case, and attributes the divergence to assumptions about server and accelerator shipment trajectories.

## Limitations and conflicts

Boundary mismatch is the central problem: IEA's 415 TWh and LBNL's 192 TWh are produced by different models with different treatment of crypto mining, on-site generation, and what counts as a data centre. The IEA global figure is itself an estimate, not a measurement — few countries publish metered data-centre consumption (Ireland is the exception, see 019). The IEA 2024 baseline is now over a year old and predates the 2025-2026 accelerator shipment surge that drove LBNL to revise its own trajectory upward. Any "US uses X% of the world's data-centre electricity" statement should be read as a ratio of two independently-modelled estimates with a plausible range of roughly 40-50%, not as a measured quantity.

## Relation to existing corpus

**Same source as `../ghg/023-iea-2025-energy-and-ai-datacentre-electricity.md`**, which captures the IEA baseline itself. This file is retained for a materially different finding: the arithmetic verification of the circulating US-share claim, which requires combining the IEA denominator with a separate US numerator and which neither source states on its own. For the IEA figures and their limitations as a standalone dataset — including that the IEA reports no AI-specific figure and attributes AI through an "accelerated servers" hardware proxy — cite the ghg file. Cite this one only for the share calculation and its boundary caveat. Supplies the global denominator that `016-lbnl-2026-us-dc-energy-2025-update.md` does not provide.

---
Retrieved: 2026-09-19
Search: WebSearch "US 40% of world data center electricity 2026 dataset IEA Ember"; Serper "IEA Energy and AI Observatory 2026 data centre electricity consumption by country". Forbes article itself returned HTTP 403 to automated retrieval and was not read.
