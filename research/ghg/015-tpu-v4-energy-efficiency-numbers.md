# TPU v4 in Google Cloud: 2.85x less energy and 18.3x less operational CO2e than a hypothetical on-premise accelerator, with 6.4x of that ratio coming from market-based electricity accounting

**Topic:** GHG emissions — accelerator and data-centre efficiency claims, and what drives them
**Source:** Norman P. Jouppi, George Kurian, Sheng Li, Peter Ma, Rahul Nagarajan, Lifeng Nai, Nishant Patil, Suvinay Subramanian, Andy Swing, Brian Towles, Cliff Young, Xiang Zhou et al. — Google, 2023
**Type:** peer-reviewed (industrial product track, ISCA 2023)
**URL:** https://doi.org/10.1145/3579371.3589350 (open preprint: https://arxiv.org/abs/2304.01433)
**Published:** 2023-06

## Finding

The abstract's claim that TPU v4 in Google Cloud uses "~2-6x less energy and produces ~20x less CO2e than contemporary DSAs in typical on-premise data centers" decomposes into three separable factors, only one of which is about the chip. Section 7.6 works it out: a conservative 2x chip performance-per-Watt advantage, multiplied by the ratio of worldwide average PUE (1.57) to Google's PUE (1.10), gives 2.85x less energy; multiplying that by the ratio of the IEA global average grid factor (0.475 kgCO2e/kWh) to Google's Oklahoma factor after hourly-matched renewable purchases (0.074 kgCO2e/kWh) gives 18.3x, which the abstract rounds to ~20x. The electricity factor alone contributes 6.4x, more than twice the contribution of hardware and facility efficiency combined. The comparator is a hypothetical recent accelerator in an average on-premise data centre, not a measured system.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Operational CO2e ratio vs on-premise DSA | 18.3x (abstract: ~20x) | 2.85 × 0.475 ÷ 0.074; operational electricity only, no embodied |
| Energy ratio used in that calculation | 2.85x | 2 × 1.57 ÷ 1.10; modelled |
| Chip performance/Watt vs contemporary DSA | ~2x-6x | the abstract's "2-6x less energy"; inferred from A100 and IPU comparisons, with 2x taken as the conservative end for the CO2e calculation |
| Grid factor charged to the on-premise comparator | 0.475 kgCO2e/kWh | IEA global average electricity carbon intensity, not a US or local grid value |
| Grid factor charged to Google | 0.074 kgCO2e/kWh | market-based: hourly-matched renewable energy purchases in Oklahoma |
| Contribution of the grid-factor ratio to 18.3x | 6.4x | 0.475 ÷ 0.074 |
| PUE assumed for the comparator | 1.57 | worldwide average, cited |
| PUE assumed for Google | 1.10 | Google fleet average, self-reported |
| Carbon-free energy share | 88% Oklahoma 2021 vs 40% US average | Google self-reported CFE; all Google Cloud TPU v4s are in Oklahoma |
| Per-chip performance vs TPU v3 | 2.1x | measured, production silicon |
| Performance/Watt vs TPU v3 | 2.7x | measured |
| vs Nvidia A100 | 1.2-1.7x faster, 1.3-1.9x lower power | similar-sized systems, MLPerf-class workloads |
| vs Graphcore IPU Bow | 4.3-4.5x faster | similar-sized systems; IPU TDP 300 W |
| System scale | 4,096 chips, ~10x faster overall than TPU v3 | 4x more chips × 2.1x per chip; deployed since 2020 |
| LLM training utilisation | ~60% of peak FLOPS/s average | measured on the 4,096-chip system |
| SparseCores | 5x-7x speedup on embedding-heavy models for 5% of die area and power | measured |
| Optical circuit switches | <5% of system capital cost, <3% of system power | measured |

## Methodology

The efficiency claim follows Google's "4Ms" framework (Model, Machine, Mechanization, Map). Model is held at 1.0 by assuming identical workloads. Machine is chip performance-per-Watt, estimated rather than measured against competitors because the MLPerf power benchmark was still in progress. Mechanization is PUE. Map is grid carbon intensity. TPU v4's own performance and power figures come from production systems running Google workloads; every figure attached to the comparator is assumed or taken from published averages. No life-cycle or embodied component is included; the paper says "operational CO2e" throughout.

## Limitations and conflicts

Every author is a Google employee and the result supports Google's cloud offering. The comparison is asymmetric in a way the paper does not flag: Google's side gets a market-based, contractually-matched electricity factor while the comparator gets the IEA global average, a figure that includes grids far dirtier than any US region a competitor would plausibly use. Because the grid-factor ratio supplies 6.4x of the 18.3x, the headline is more sensitive to the two electricity factors chosen than to anything about the silicon. The comparator itself is hypothetical, its PUE is a worldwide average rather than a best-in-class on-premise figure, and the 2x chip advantage is the conservative end of a range the paper estimates rather than measures. Embodied emissions are absent entirely, so the figure says nothing about lifetime carbon.

## Relation to existing corpus

`research/ghg/027-schneider-2025-tpu-lifecycle-embodied-emissions.md` extends the same programme to full lifecycle for later TPU generations and quantifies the accounting effect left implicit here: Google's own operational emissions are 2.7x higher under location-based than market-based accounting. `research/ghg/028-google-2026-environmental-report-accounting-gap.md` and `research/ghg/029-microsoft-2026-sustainability-report-fy25.md` document the same market-versus-location gap at corporate scale. `research/ghg/030-guidi-2026-us-hyperscale-carbon-intensity.md` measures US hyperscale sites at a location-based 545 gCO2/kWh, against the market-based 74 g Google applies to itself here.

---
Retrieved: 2026-09-19
Search: DOI 10.1145/3579371.3589350; arXiv 2304.01433 PDF extracted locally
