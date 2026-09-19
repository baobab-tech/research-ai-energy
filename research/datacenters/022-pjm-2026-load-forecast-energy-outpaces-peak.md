# PJM's 2026 forecast has energy demand growing at 5.3%/year against summer peak at 3.6% — the signature of flat-profile data-centre load, and twelve zones are now explicitly adjusted for it

**Topic:** Data-centre infrastructure — regional load forecasting, PJM / Northern Virginia
**Source:** PJM Interconnection, Resource Adequacy Planning Department, *2026 PJM Load Forecast Report*
**Type:** grid-operator filing
**URL:** https://www.pjm.com/-/media/DotCom/library/reports-notices/load-forecast/2026-load-report.pdf
**Published:** 2026-01-14

## Finding

PJM projects net energy load growing 5.3% per year over ten years while summer peak grows 3.6% and winter peak 4.0%. Energy rising faster than peak means the added load runs at a higher load factor than the existing system — the arithmetic signature of always-on data-centre demand rather than weather-driven residential or commercial growth. Twelve transmission zones plus Dominion have had their forecasts manually adjusted for "growth in data center load," meaning PJM's statistical models could not reproduce the trajectory from economic and weather drivers and the growth had to be inserted by hand. Winter peak now grows faster than summer peak, which changes which season sets resource adequacy requirements.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Summer peak growth, 10-year | 3.6%/yr average | RTO total |
| Summer peak, 2036 | 222,106 MW (+65,733 MW over 10 years) | |
| Summer peak, 2046 | 253,077 MW (+96,704 MW over 20 years) | 2.4%/yr |
| Winter peak growth, 10-year | 4.0%/yr average | |
| Winter peak, 2035/36 | 204,650 MW (+66,980 MW) | |
| Winter peak, 2045/46 | 236,693 MW (+99,023 MW) | 2.7%/yr |
| Net energy growth, 10-year | 5.3%/yr average | |
| Net energy, 2036 | 1,437,629 GWh (+581,554 GWh over 10 years) | |
| Net energy, 2046 | 1,667,075 GWh (+811,000 GWh over 20 years) | 3.4%/yr |
| Zonal 10-year peak growth spread | −0.2% to 6.4%, median 1.6% | Growth is concentrated, not general |
| Zones adjusted for data-centre load growth | AEP, ATSI, APS, BGE, COMED, DAYTON, DLCO, JCPL, METED, PECO, PEPCO, PL | Manual load adjustments |
| DOM (Dominion Virginia) | adjusted for data-centre load growth *and* a voltage optimisation programme | Northern Virginia zone |
| Behind-the-meter solar/battery offset | −2,564 MW (2026, 3rd IA), −4,414 MW (2028 RPM auction), −1,630 MW (2031 RTEP) | S&P Global SPGCI forecast |

## Methodology

PJM's econometric forecast uses Itron end-use data for appliance saturation, efficiency and intensity, consistent with EIA's 2025 Annual Energy Outlook, plus zone-supplied load research. The important qualifier is the "Load Adjustments" mechanism: where the model cannot capture large unanticipated load changes, PJM overrides it zone by zone. The data-centre component of PJM's forecast is therefore substantially an assumption input rather than a model output, and the report does not publish a GW figure for the data-centre adjustment itself.

The median zonal 10-year growth rate of 1.6% against an RTO average of 3.6% shows the growth is concentrated in a minority of zones. Most of PJM is growing slowly; a handful of zones carry the aggregate.

## Limitations and conflicts

PJM has a direct interest in the forecast: it sets capacity auction obligations and justifies transmission expansion, and a high forecast supports higher capacity procurement. The data-centre adjustments are not decomposed into announced-versus-contracted-versus-energised capacity, so the same announcement-inflation risk that ERCOT's Batch Zero screen exposes (see 017) is embedded here without a screen visible in this document. PJM did subsequently trim its near-term forecast on stricter data-centre screening criteria, which this January 2026 edition predates. Behind-the-meter solar and battery forecasts are purchased from S&P Global. Load-adjustment detail lives in tables B-9/B-9b and a Supplement not examined here.

## Relation to existing corpus

No direct overlap — no PJM or regional load-forecast material existed in the folder. The load-factor point is the demand-side complement to the PUE critique in `023-verrus-2026-pue-critique-pux.md`: data-centre load is hard on the grid because it is flat and additive, not because it is peaky.

---
Retrieved: 2026-09-19
Search: Serper "PJM 2026 data center load forecast GW interconnection" → PJM PDF, text extracted locally
