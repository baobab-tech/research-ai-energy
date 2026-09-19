# For every dollar the ICT sector sent to renewable and nuclear energy in 2022, more than four went to oil and gas

**Topic:** narrative — AI applied to fossil-fuel production, the counter-case to "AI for climate"
**Source:** Gauthier Roussilhe, Béatrice Dromard, Srinjoy Mitra, 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2604.26539
**Published:** 2026-04-29

## Finding

Input-output analysis of economic flows from 2000 to 2022 shows that 2% of annual ICT sector inputs go to oil and gas, and that in 2022 the flow from ICT to oil and gas was more than four times the flow from ICT to renewable and nuclear energy combined — this in a year when global investment in renewables was roughly twice that in fossil fuels. The relationship predates generative AI by two decades. The paper also works a documented contract case: Microsoft's cloud and AI deal with ExxonMobil's XTO Energy in the Permian Basin, publicly targeted at 50 000 additional barrels per day, implies roughly 6.7 MtCO2 of added emissions in 2025 alone — 43% of Microsoft's 2024 market-based footprint, or 27% of its location-based footprint. Emissions from such projects are not in the vendor's scope 3.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| ICT inputs going to O&G, 2000–2022 average | 2% of annual ICT inputs | Input-output analysis (monetary flows) |
| O&G inputs going to ICT | 0.4% average over the period | Reverse direction |
| ICT→O&G vs ICT→renewable & nuclear, 2022 | >4:1 | Monetary |
| Context: global investment, 2025 | $2.2 tn renewables vs $1.1 tn fossil | IEA-referenced; the ICT flow runs opposite to the capital flow |
| Microsoft–XTO Energy case: added production 2019–2025 | 54 293 750 barrels | Linear extrapolation, 15% average downtime, 50 000 bbl/d reached in final year |
| Added emissions, cumulative 2019–2025 | 23 447 842 tCO2 | 431.87 kgCO2/barrel (US EPA, conventional oil) |
| Added emissions, 2025 alone | 6 699 383 tCO2 (~6.7 Mt) | Same factor; authors call this conservative — shale is more energy-intensive than conventional |
| As share of Microsoft's 2024 footprint | 43.1% market-based (of 15 543 000 tCO2e); 26.7% location-based (of 25 095 511 tCO2e) | Not included in Microsoft scope 3 |
| Valero/AVEVA refinery case: added emissions | 58–583 ktCO2e per plant per year, up to 3 500 ktCO2e for all identified savings | ITU-T Supplement 54 monetary emissions factor: 11 667 kgCO2e per k$, from Valero 2024 profit $2.76 bn and 32.2 MtCO2e scope 1+2 |
| Wood Mackenzie "Every Last Drop" scenario, translated | 470–1 000 bn additional barrels by 2050 → 7.8–16.6 GtCO2e/yr | Authors' own translation; they label these estimates "unrealistic, or even absurd" |

## Methodology

Two distinct methods with different strengths. The macro picture is input-output analysis of monetary flows between ICT and O&G divisions, 2000–2022 — reliable for orders of magnitude and trend, but the authors state plainly that IOA "does not allow us to establish a causal link between economic flows."

The micro picture is two case studies using vendor-published performance claims taken at face value and converted to emissions via published factors. This is the mirror image of the avoided-emissions method: where a vendor claims its technology enabled a saving, the same claim can be converted into enabled *additional* production. The Valero case uses a monetary emissions factor (ITU-T Supplement 54), which is coarse — it assumes emissions scale with profit.

The paper's strongest structural point is asymmetry of accounting. Vendors publish avoided-emissions figures for climate-positive deployments and publish nothing for fossil-production deployments, even where both rest on the same class of causal claim by the same vendor. Microsoft claims neither the 6.7 Mt from XTO nor any quantified AI-for-climate benefit (see `narrative/022-google-2026-enabled-emissions-41mt.md`); Google claims 41 Mt of benefit and discloses no corresponding enabled fossil production.

The paper also traces the GPU lineage: NVIDIA's CUDA release in 2006 and the adoption of GPGPU for seismic simulation and reservoir analysis in "digital oilfields" preceded and helped fund the hardware base that generative AI now runs on. The authors present this as a hypothesis about causality, not an established result.

## Limitations and conflicts

Preprint, not peer reviewed. The case-study emissions figures are the authors' own extrapolations from vendor marketing claims and press reporting, not from audited production data; if the vendor claims are inflated, so are the derived emissions. The 431.87 kgCO2/barrel EPA factor is for conventional oil applied to Permian shale, which the authors acknowledge understates. The Wood Mackenzie translation (7.8–16.6 GtCO2e/yr) is explicitly presented by the authors as a reductio, not an estimate, and should not be cited as one. IOA cannot attribute causation. Roussilhe is an independent researcher working on ICT environmental footprints with a consistently critical prior; Mitra is at the University of Edinburgh. No funding statement is present.

## Relation to existing corpus

No direct overlap — the repository contained nothing on AI applied to fossil-fuel extraction. Provides the quantitative counterpart to the conceptual category "AI against sustainability" set out by Kunkel et al., 2026 (https://arxiv.org/abs/2606.23192), which distinguishes AI's own footprint, AI for sustainability, and the environmental harm of AI's applications.

---
Retrieved: 2026-09-19
Search: arXiv `all:"avoided emissions"`, submissions since 2025-09; full PDF retrieved and text-extracted
