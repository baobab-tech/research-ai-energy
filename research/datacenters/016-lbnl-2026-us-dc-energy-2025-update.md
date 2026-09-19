# LBNL revises US data-centre electricity to 192 TWh in 2024 and 649 TWh by 2030, and converts that to 148 GW of interconnection capacity

**Topic:** Data-centre infrastructure — national demand baseline, buildout in GW, fleet PUE
**Source:** Smith, S.J., Hubbard, A., Newkirk, A., Ganeshalingam, M., Holecek, B., Sartor, D., Mills, M., Shehabi, A. — Lawrence Berkeley National Laboratory, 2026 (LBNL-2001758)
**Type:** agency report (peer reviewed, DOE national laboratory)
**URL:** https://www.energy.gov/documents/united-states-data-center-energy-usage-report-2025-update
**Source note:** DOE landing page, verified 200). Full PDF retrieved and text-extracted from https://www.rtoinsider.com/wp-content/uploads/2026/06/data-center-energy-usage-2025-update.pdf (verified 200). Canonical identifiers printed on the report's own cover page: eScholarship permalink https://escholarship.org/uc/item/33m6w3x0 and DOI https://doi.org/10.71468/P1RP4F — both return HTTP 403 to automated retrieval.
**Published:** 2026-06-18

## Finding

The successor to the 2024 Shehabi et al. report revises the 2024 US data-centre total *down* to 192 TWh (4.7% of US electricity) while revising the forward path *up*: a Reference Case of 649 TWh in 2030, 11.8% of forecast US electricity. The downward revision of history comes from lower reported 2023-2024 GPU shipments and reduced AI-inference server power assumptions. The report also does the conversion most buildout reporting skips: applying an assumed 50% average interconnection-capacity utilisation, the 2030 Reference Case corresponds to 148 GW of grid interconnection capacity, i.e. 17.4 GW/year of new capacity from 2024. That figure is roughly one-third of the large-load interconnection requests sitting in ERCOT's queue alone (see 017), which quantifies how far requested capacity exceeds modelled need.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| US data-centre electricity, 2024 | 192 TWh; 4.7% of US electricity | Bottom-up from IT shipment data; excludes cryptocurrency mining; includes servers, storage, network, facility infrastructure |
| 2028 Reference Case | 464 TWh | Mid-range of the 2024 Report's band |
| 2030 Reference Case | 649 TWh; 11.8% of US electricity | Denominator from NERC 2025 Long-Term Reliability Assessment |
| 2030 Compounded Uncertainty range | 521–843 TWh (9.5–15.3%) | −19.6% to +29.9% vs Reference |
| High Inference Energy sensitivity | 782 TWh (+20.6%) | Raised idle power and utilisation of AI inference servers |
| Consolidated Deployment sensitivity | 578 TWh (−10.8%) | Lower forecast IT equipment installations |
| Low Accelerator Lifetime sensitivity | 590 TWh (−9.1%) | Shorter assumed AI chip operating life |
| Interconnection capacity implied, 2030 | 148 GW | Annual average power draw ÷ assumed 50% utilisation |
| Implied annual capacity addition | 17.4 GW/yr, 22% CAGR, 2024–2030 | Same assumption |
| National average PUE | 1.55 (2018) → 1.45 (2024) → 1.36 (2030) | Modelled, all facility types |
| PUE of AI-serving facilities | 1.145 (2024) → 1.136 (2030) | Modelled; authors expect no material industry-wide AI-PUE change |
| Infrastructure share of DC electricity | 36% (2018) → 31% (2024) | Falls because AI load concentrates in low-PUE liquid-cooled sites |
| AI servers, 2030 Reference | 84% of server energy, 55% of all DC energy | — |
| Servers shipped | 5.9M (2024) → 9.1M (2028) | Omdia/IDC/S&P shipment data; 20% above 2024 Report |
| Data centres' share of 2024–2030 US load growth | 33% | Against NERC's implied 926 TWh (24%) total growth |

## Methodology

Bottom-up stock model: IT equipment shipments (Omdia Research, S&P Global, IDC) build an installed base; per-device annual energy models and cooling-system simulations are applied; results are multiplied by modelled PUE by facility type and location. 2024 is the last historical year — primary shipment data run only through Q3 2025, so 2025 onward contains projection. Five discrete scenarios plus a compounded high/low band. 2028→2030 values are extrapolated (linear or exponential) rather than modelled from shipment data.

The PUE treatment is where the metric's blind spot shows in the authors' own numbers. Aggregate PUE improves from 1.45 to 1.36 by 2030, but the improvement "primarily reflects the continued shift in server energy use into the types of data centers that have the lowest PUEs" — a mix shift, not efficiency gains at any given site. AI-facility PUE is essentially flat (1.145 → 1.136). Because PUE is a ratio to IT load, the +20.6% High Inference Energy scenario — driven entirely by idle power and utilisation of the IT equipment itself — does not move PUE at all. Falling PUE and sharply rising total energy are fully compatible.

## Limitations and conflicts

Funded by the DOE Industrial Technologies Office under Contract DE-AC02-05CH11231. Input shipment data are purchased from commercial analysts (Omdia, S&P Global, IDC) and are not independently auditable. Manufacturer and data-centre-operator experts reviewed the assumptions, which imports industry judgement into a government estimate. Crypto mining is excluded, so this is not a total-facility number. The 50% interconnection utilisation assumption is explicitly acknowledged as poorly documented ("Current utilization of interconnection capacity is not well documented but is estimated to be around 50%") and it drives the entire 148 GW figure linearly — at 70% utilisation the same energy implies ~106 GW. The authors state that uncertainty in PUE values, included in the 2024 Report, is *not* carried into this update's uncertainty range.

## Relation to existing corpus

**Supersedes `../ghg/025-shehabi-2024-lbnl-us-data-center-energy.md`** (LBNL-2001637, the 2024 Report). This is its official successor by the same group. Where they differ, cite this one: the 2023 figure of 176 TWh is revised down (2024 is now 192 TWh, and the report states revised historical values fall slightly below the 2024 Report), the 2028 range of 325-580 TWh is replaced by a 464 TWh Reference Case, and the horizon extends to 2030. Keep the 2024 Report for the historical 2014-2018 series and for the fact that the inflection was identified in 2024. Directly contradicts `015-setyo-2025-dc-energy-efficiency-thermal-review.md`, which reports an average PUE of 2.23 "much worse than hyperscaler claims"; LBNL's US fleet-weighted figure is 1.45 for 2024. The two are not measuring the same population (Setyo et al. average across published studies including small legacy facilities; LBNL weights by energy, so hyperscale dominates). Provides the national denominator missing from `007-li-2025-ai-water-growth-projections.md` and `012-lei-2025-us-small-midsize-dc-cbecs.md`.

---
Retrieved: 2026-09-19
Search: Serper "LBNL 2024 United States Data Center Energy Usage Report PUE" → full PDF text extraction
