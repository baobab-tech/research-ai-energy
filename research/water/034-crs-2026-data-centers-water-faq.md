# CRS: Direct Data-Centre Water Is ~2% of US Water Consumption; IEA Puts the Direct:Indirect Split at 40:60; No Federal Agency Has Ever Measured It

**Topic:** Water — US federal framing of withdrawal vs consumption, WUE boundary, cooling-technology water/energy trade-off, and the measurement gap
**Source:** Congressional Research Service — Folger, Humphreys, Carter, Clark, Gatz, Normand, Stern, 2026
**Type:** agency report (CRS Report R49057)
**URL:** https://www.congress.gov/crs_external_products/R/PDF/R49057/R49057.1.pdf
**Source note:** landing page https://www.congress.gov/crs-product/R49057 blocks automated requests
**Published:** 2026-07-31

## Finding

CRS states that direct data-centre water consumption is approximately 2% of total US water consumption, and that the IEA's *Energy and AI* splits total data-centre water 60% indirect (at power plants) and 40% direct. On the same IEA basis, a 100 MW US data centre consumes the water of roughly 6,500 households in total and 2,600 households directly. CRS also states that no federal agency has ever systematically assessed data-centre water use: USGS classified data centres under "commercial" until 1995 and has published no separate commercial-sector withdrawal estimate since. The report is explicit that WUE as normally reported measures only direct facility water and excludes the water consumed generating the electricity, and that a comprehensive WUE covering both "may be more appropriate."

## Key Data

| Metric | Value | Boundary / source |
|---|---|---|
| Direct DC water as share of US water consumption | ~2% | Direct only; AWWA, *Cooling the Cloud*, Oct 2025 |
| IEA direct : indirect split | 40% : 60% | IEA *Energy and AI*, April 2025, p. 242 |
| 100 MW US data centre, total water | ≈ 6,500 households' consumption | IEA; averaged across cooling strategies |
| 100 MW US data centre, direct water | ≈ 2,600 households' consumption | IEA |
| US DC direct water use, 2023 | ~17 billion gallons | LBNL 2024 (= 66 billion L) |
| US DC direct water use, 2014 | 5.6 billion gallons | LBNL 2024 |
| Share of DC water from public water systems | 97% | Bluefield Research, June 2025 |
| US water-related DC expenditure to 2030 | >$41 billion | Bluefield Research |

### Definitions as CRS uses them

- **Consumption**: water withdrawn and no longer available for reuse — permanently removed from the original source by evaporation or other irreversible processes, including deep-well injection of wastewater.
- **WUE**: total data-centre water consumption ÷ IT equipment electricity demand. Measures direct facility water only; excludes off-site generation water.

### Cooling technologies and the water-energy trade-off

| System | Water | Energy |
|---|---|---|
| Water-cooled chiller with cooling tower (evaporative) | Highest WUE, i.e. most water; driven by cooling-tower evaporation | Generally more energy-efficient than air-cooled chillers |
| Air-cooled chiller / waterless | No water | Comparatively more energy |
| Waterside economiser | Reduces WUE by cutting mechanical chiller and compressor heat | Reduces energy |
| Airside economiser | Allows chilled-water shutdown in favourable weather, reducing water | |
| Raising setpoint temperatures | Reduces water | Operational, no capital |

CRS states the trade-off plainly: evaporation-based cooling is generally more energy-efficient than air-cooled chillers or other waterless systems; waterless systems use more energy. Liquid cooling is described as more efficient than air cooling but potentially not cost-effective for small and midsize facilities; immersion and two-phase cooling are described as being explored, not deployed.

### Measurement gap

No federal systematic assessment of data-centre water use exists. USGS classified data centres as commercial (NAICS 518210) through 1995 and has published no separate commercial-sector withdrawal estimate since. The 2025 USGS Integrated Water Availability Assessment 2010-20 covers public supply, irrigation and thermoelectric cooling at subwatershed scale and monthly intervals — data centres are not a category. Texas's PUC is running an energy-and-water-use survey of data centres and cryptocurrency mining facilities (Project 59281), reporting to the Legislative Budget Board and governor by end of 2026. Bills on data-centre water data have been introduced in the 119th Congress, mostly concerning collection and publication.

## Methodology

A synthesis, not new measurement. CRS compiles published estimates (LBNL 2024, IEA 2025, AWWA 2025, Bluefield Research 2025) and describes the federal statutory and regulatory landscape. Every number is sourced to a third party; CRS produces none of its own.

## Limitations and conflicts

CRS is non-partisan and produces reports at congressional request; no funding conflict. The constraint is that it inherits the weaknesses of what it cites:

- The ~2% figure comes from AWWA, a water-utility trade association, and covers direct consumption only. Against the 40:60 IEA split, the total-water share would be about 5%.
- The IEA 40:60 split is an average "across the various cooling strategies" with no distribution given, and IEA does not publish the underlying facility data.
- The 97% public-water-supply figure is from a commercial research firm's press release.
- The cooling-technology comparison is qualitative throughout: CRS names the direction of every trade-off but quantifies none of them. No L/kWh values, no energy penalty percentages.

## Relation to existing corpus

**Same document, different findings from** `research/community/026-crs-2026-data-centers-water-municipal-supply.md`, which takes the institutional material from this CRS report — 97% municipal supply, non-public rates and service agreements, the Marana AZ refusal ordinance. This excerpt takes the quantitative and boundary material: the ~2% share, the IEA 40:60 split, the WUE definition, the cooling trade-offs and the federal measurement gap. No overlapping numbers except the 17 billion gallon LBNL direct-use figure and the 97% supply share. Brings the IEA *Energy and AI* water numbers into the corpus for the first time (the shared brief lists IEA as a missing foundational source), and supplies the US federal definitional framing. The IEA 40:60 direct:indirect split sits between the competing ratios in the corpus: `research/water/029-shehabi-2024-lbnl-direct-vs-indirect-water.md` gives 1:12 for all US data centres on a consumption basis, `research/water/032-guidi-dominici-2026-scope1-scope2-water-geography.md` gives 1:3 for hyperscale, and IEA gives 1:1.5. Three credible sources, three answers — the indirect multiplier is the largest open quantitative question in this literature. CRS's "~2% of US water consumption, locally material" framing is the national-aggregate counterpart to the utility-scale burden argument in `research/water/033-akinade-2026-water-consumption-impact-utility-burden.md`, which puts the national figure at 0.6-1.1% of public withdrawals by 2030.

---
Retrieved: 2026-09-19
Search: WebSearch "AGU Advances 2026 data center water use" → congress.gov R49057; PDF via congress.gov crs_external_products (crsreports.congress.gov returns 403)
