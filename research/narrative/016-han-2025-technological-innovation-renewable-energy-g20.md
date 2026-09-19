# In a G-20 panel 1995-2022, a 1% rise in resident patent applications associates with a 0.33% rise in the renewable share of energy; the variable is patents, not AI

**Topic:** Narrative — the macro "innovation drives decarbonisation" claim and what its evidence measures
**Source:** Han, Dong, Guo, Aslam & Xu, 2025
**Type:** peer-reviewed
**URL:** https://doi.org/10.1038/s41598-025-85182-0
**Published:** 2025-01

## Finding

Technological innovation, measured as the number of patent applications filed by residents, associates
with a higher renewable share of final energy consumption in G-20 countries over 1995-2022: 0.33% in the
long run and 0.17% in the short run for each 1% increase in patents. The estimator is PMG-ARDL, a
cointegration model that identifies a long-run equilibrium relationship among non-stationary series. It is
correlational, not causal, and imposes a single long-run coefficient across all countries. An FMOLS
robustness check puts the same elasticity at 0.29. The paper contains no AI variable, no computing variable
and no data-centre variable; the innovation measure counts all resident patents of every technology class.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Technological innovation proxy | resident patent applications, count | World Development Indicators; log-transformed |
| Renewable energy variable | renewable share of total final energy consumption, % | WDI; log-transformed |
| Innovation elasticity, long run | +0.33% per 1% | PMG-ARDL pooled long-run coefficient |
| Innovation elasticity, short run | +0.17% per 1% | PMG-ARDL, heterogeneous across countries |
| Same elasticity under FMOLS | +0.2896 (s.e. 0.0887) | Fully modified OLS robustness check |
| Environmental pollution on renewables, long run | -1.81% per 1% CO2 | PMG-ARDL; short run -0.64% |
| Environmental pollution on renewables, FMOLS | -1.3207 (s.e. 0.1170), p < 0.001 | FMOLS |
| Economic freedom on renewables, FMOLS | +0.9595 (s.e. 0.2322) | FMOLS; index from the Heritage Foundation |
| Panel | G-20 countries, 1995-2022 | Annual; WDI and Heritage Foundation index |

## Methodology

A pooled mean group ARDL panel estimated on log-transformed annual series with the renewable share as the
dependent variable and technological innovation, GDP, financial advancement, economic freedom and CO2
emissions as regressors. PMG constrains the long-run coefficients to be identical across countries while
allowing short-run dynamics to vary. Stationarity is tested with CIPS and CADF after establishing
cross-sectional dependence; cointegration is confirmed before estimation. FMOLS and DOLS are run as
robustness checks.

## Limitations and conflicts

No funding statement, industry involvement or competing interest is apparent in the article.

Patent counts measure filing behaviour, not deployed technology, and say nothing about which technologies
were patented. A country's renewable share and its patent filings both track income and institutional
capacity, which the model controls for only through GDP and an economic-freedom index. PMG-ARDL identifies
a cointegrating relationship; it does not identify a causal effect, and the paper's language ("leads to",
"boosts") outruns what the estimator supports.

The pooled long-run restriction forces one elasticity on economies as different as Indonesia and Germany.
The paper's own descriptive statistics report that the innovation variable is highly right-skewed with high
kurtosis and outliers, which in a G-20 sample means China, the United States and Japan dominate the
estimate.

Nothing in the paper concerns AI, computing or data centres. Applying the result to AI requires assuming
that AI patents behave like the average patent and that AI deployment behaves like the average deployed
innovation, neither of which is tested here.

The CO2 result runs in the direction the paper treats as counterintuitive: higher pollution associates with
lower renewable adoption, which is a composition effect of fossil-dependent economies rather than evidence
about innovation.

## Relation to existing corpus

No direct overlap. The corpus contains no other panel estimate of the innovation-to-renewables
relationship. Its use here is as the macro evidence base most often invoked behind the claim that
technology investment is itself a decarbonisation strategy, and as a demonstration of how far that evidence
sits from anything AI-specific.

---
Retrieved: 2026-09-19
Search: DOI 10.1038/s41598-025-85182-0, open-access full text at nature.com
