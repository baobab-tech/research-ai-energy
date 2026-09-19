# Google's 0.26 mL Per Prompt Is an On-Site Cooling Figure; Adding Generation Water Raises It 179% to 0.725 mL

**Topic:** Water — reconciling the Google vs Li et al. per-query gap; on-site (Category 2 / WUE) vs off-site (generation) accounting boundary
**Source:** Sharma, Tiwari, Kaur, Park, Pinsky (Northeastern University; Boston University MET / Global Development Policy Center), 2026
**Type:** peer-reviewed (MDPI *Green*, open access)
**URL:** https://doi.org/10.3390/green1020008
**Source note:** www.mdpi.com blocks automated requests; retrievable PDF: https://mdpi-res.com/d_attachment/green/green-01-00008/article_deploy/green-01-00008.pdf
**Published:** 2026-09-01

## Finding

Google's 0.26 mL per median Gemini text prompt is a Category 2 water-usage-effectiveness figure: freshwater consumed inside the facility for cooling only, excluding water consumed at upstream generation plants. The authors reconstruct it to within 2.3% from Google's own published inputs (0.24 Wh/prompt, fleet WUE 1.15 L/kWh, 8% overhead exclusion), obtaining 0.254 mL. Adding the water consumed generating that electricity — at a US thermoelectric intensity of 1.80 L/kWh — adds 0.471 mL, for a boundary-complete total of 0.725 mL, 179% above the disclosure. The boundary choice therefore accounts for a factor of ~2.8, not the 40-100x gap against Li et al.; the remainder is prompt length and the choice of median. The same paper's tier analysis puts a long Gemini prompt at 9.2 Wh and 28 mL total water — inside Li et al.'s 10-25 mL range.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Google disclosed water/prompt | 0.260 mL | On-site cooling, WUE Category 2 (ISO/IEC 30134-9), median text prompt |
| WCI reconstruction, direct term | 0.254 mL | Same boundary, from Google's own 0.24 Wh, WUE 1.15 L/kWh, 8% overhead exclusion |
| Reconstruction agreement | 2.3% | Internal consistency check, explicitly not independent validation |
| WCI indirect term | 0.471 mL | Electricity-generation water, EWIF 1.80 L/kWh, via PUE × EWIF |
| WCI total | 0.725 mL | Direct + indirect; +179% over Google's disclosure |
| Gemini short prompt | 0.32 Wh; 0.34 direct / 0.63 indirect / 0.97 mL total | Uniform national EWIF |
| Gemini medium prompt | 1.6 Wh; 1.7 / 3.1 / 4.8 mL | " |
| Gemini long prompt | 9.2 Wh; 9.7 / 18 / 28 mL | " |
| OpenAI GPT-4o public figure | 0.322 mL | Boundary unstated by OpenAI; WCI direct term with proxied WUE gives 0.065 mL, total 0.750 mL |
| Mistral Large 2 (AFNOR LCA) | ~45 mL per response | Amortises training + hardware manufacture across inferences — not operational-only |
| Google fleet WUE | 1.15 L/kWh | Google self-reported, Category 2 |
| Microsoft fleet WUE | 0.27 L/kWh (paper also cites ~0.30 globally) | Microsoft self-reported |
| OpenAI WUE proxy | 0.19 L/kWh (AWS hyperscale proxy) | Not OpenAI-disclosed; paper flags this as its weakest parameter |
| Industry-average WUE | ~1.8 L/kWh | The Green Grid |

### Regional EWIF (2024 generation mix), two hydro conventions

| Region | Hydro share | Operational convention | Reservoir-evaporation convention |
|--------|-------------|------------------------|----------------------------------|
| Oregon | 41% | 0.30 L/kWh | 28.18 L/kWh |
| Iowa | 1% | 0.57 L/kWh | 1.50 L/kWh |
| Arizona | 4% | 1.43 L/kWh | 4.15 L/kWh |
| Virginia | 1% | 1.53 L/kWh | 2.21 L/kWh |
| Reference case | n/a | 1.80 L/kWh | 1.80 L/kWh |

Per-source intensities used: 2.20 L/kWh wet-cooled coal, 3.30 L/kWh nuclear, 0.80 L/kWh gas; hydro either 0 (operational) or 68 L/kWh (reservoir evaporation). National average including hydro: 7.60 L/kWh.

## Methodology

WCI = direct + indirect, per query. Direct: query energy × (1 − overhead exclusion) × WUE. Indirect: query energy × PUE × EWIF. WUE is Category 2, which counts only water consumed inside the facility, so the EWIF term recovers upstream water without double counting. A third term weights total water by Aqueduct 4.0 Baseline Water Stress (BWS 0-5) as a scarcity multiplier, reported in "mL-equivalent": a 4.8 mL medium Gemini prompt becomes ~24 mL-equivalent in Phoenix (WSI 5.0), 0.76 in Ashburn VA (0.158), 0.62 in Council Bluffs IA (0.128), and 0.000 in the Columbia/Hood sub-basin in Oregon (0.000). 24 scenarios (2 providers × 3 prompt tiers × 4 regions), with Sobol sensitivity and 5th-95th percentile bands. All inputs are published disclosures or literature values; nothing is independently measured.

The hydro-accounting result: whether reservoir evaporation is allocated to generation reverses the regional ordering. Oregon is the least water-intensive of the four grids under the operational convention (0.30 L/kWh) and the most water-intensive under the reservoir convention (28.18 L/kWh), a ~94x swing. Oregon overtakes the other three at any hydro intensity above roughly 3.1 L/kWh, against the 68 L/kWh adopted.

## Limitations and conflicts

No external funding declared; no conflicts declared; authors are academic (Northeastern, Boston University). Code at https://github.com/anacodicAI-labs/hidden-thirst.

The reconstruction is arithmetic on Google's published inputs, so it verifies the paper's implementation, not Google's measurement. The authors say so explicitly: external validation would need independently measured facility water attributable to a known query volume, and "no such measurement is publicly available for any commercial LLM deployment." Google's 0.24 Wh and 1.15 L/kWh remain unaudited self-reported values, and the whole chain inherits them. The OpenAI row is not a like-for-like comparison — OpenAI does not state its boundary and its WUE here is an AWS proxy. Hydro intensity of 68 L/kWh is one published value among a wide and methodologically contested range. Embodied water (training amortisation, chip fabrication) is outside the boundary throughout; the Mistral 45 mL figure shows how much that omission is worth.

## Relation to existing corpus

This is the independent verification flagged as missing in `research/water/_index.md` and in `research/water/017-google-2025-gemini-water-measurements.md`. It settles the boundary question: Google's 0.26 mL counts on-site evaporative loss only and excludes the water behind the electricity. It partially reconciles the gap with `research/water/018-li-2025-cacm-ai-water-projections.md` (10-25 mL/query): boundary explains ~2.8x, prompt-length tier explains most of the rest (a long prompt reaches 28 mL on a full boundary). It does not vindicate either side — Li et al.'s figure is a 2023-vintage estimate for a different model on Microsoft infrastructure.

---
Retrieved: 2026-09-19
Search: WebSearch "2026 critique Google Gemini per-prompt water excludes water embedded in electricity generation" → DOI 10.3390/green1020008; full text via mdpi-res.com PDF (www.mdpi.com returns 403)
