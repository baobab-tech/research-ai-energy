# AI Environmental Impact Research

A sourced corpus on the environmental footprint of AI systems: energy, emissions, water, grid
effects, and the distance between corporate environmental claims and the data underlying them.

218 excerpts, 170 unique sources. Each excerpt records one source, its numbers, the system
boundary those numbers were computed on, and what the source omits.

Last refresh: 2026-09-19.

## Scope

| Topic | Focus | Excerpts |
|-------|-------|---------:|
| [GHG emissions](research/ghg/) | Training, inference, embodied, and aggregate figures | 32 |
| [Water](research/water/) | Cooling, per-query estimates, on-site and off-site boundaries | 35 |
| [Data centres](research/datacenters/) | Buildout, interconnection, power sourcing, efficiency metrics | 25 |
| [Greenwashing](research/washing/) | Claims against underlying disclosure, by named company | 25 |
| [Policy](research/policy/) | AI Act, EED Article 12, US state and federal instruments | 23 |
| [Frugal AI](research/frugal/) | Energy measurements of efficiency techniques | 26 |
| [Grid and community](research/community/) | Prices, cost allocation, siting, environmental justice | 24 |
| [AI-for-climate narrative](research/narrative/) | Avoided-emissions claims and their counterfactuals | 28 |

## Findings

### Aggregate energy and emissions

Data centres consumed 415 TWh in 2024, about 1.5% of global electricity, rising to roughly
945 TWh by 2030 on the IEA's base case ([IEA 2025](research/ghg/023-iea-2025-energy-and-ai-datacentre-electricity.md)).
US data centres used 192 TWh in 2024, 4.7% of national electricity, with a 2030 reference case
of 649 TWh and a compounded range of 521 to 843 TWh
([LBNL 2026](research/datacenters/016-lbnl-2026-us-dc-energy-2025-update.md)).

AI-attributable emissions for 2025 are estimated at 32.6 to 79.7 MtCO2, operational only
([de Vries-Gao 2025](research/ghg/022-de-vries-gao-2025-ai-carbon-water-footprint.md)). The
floor is 2.4x below the ceiling. The estimate excludes manufacturing and is a model built on the
IEA's model, which rests on proprietary datasets that cannot be independently audited.

No operator discloses AI-specific emissions, so every figure above is inferred from total
data-centre load.

### Scope 2 accounting

Every large operator reports two Scope 2 numbers. Headline claims rest on the market-based
figure; physical grid emissions track the location-based figure. From company filings:

| Company | Market-based Scope 2 | Location-based | Ratio |
|---------|---------------------:|---------------:|------:|
| [Meta, 2024](research/washing/020-meta-2025-scope2-4394x-gap.md) | 1,358 t | 5,967,348 t | 4,394x |
| [Google, 2025](research/washing/018-google-2026-market-vs-location-based-gap.md) | 2,815,000 t | 15,148,700 t | 5.4x |
| [Microsoft, FY25](research/ghg/029-microsoft-2026-sustainability-report-fy25.md) | 2,707,428 t | 12,030,000 t | 4.4x |
| [Amazon, 2025](research/washing/022-amazon-2026-market-based-only-no-location-disclosure.md) | 3,740,000 t | not published | |

Google reports operational emissions falling 2.3% in 2025 while its electricity use rose 37%.
Its location-based Scope 2 rose 36.9%, tracking consumption. Its headline "58 Mt avoided" is
defined in its own endnotes as the difference between the two methods, with the note that the
estimate "hasn't been independently verified."

Annual volumetric matching produces this divergence mechanically. Microsoft's 10.4x increase in
reported Scope 2 came from dropping non-additional certificates, a correction Microsoft states
in its own text ([Microsoft 2026](research/washing/017-microsoft-2026-unbundled-rec-withdrawal.md)).
Independent attribution of 403 US hyperscale sites to the generating plants supplying them gives
545 gCO2/kWh, 48% above the US grid average
([Guidi et al. 2026](research/ghg/030-guidi-2026-us-hyperscale-carbon-intensity.md)).

### Water

Google reports 0.26 mL per median Gemini text prompt. Li et al. estimated 10 to 25 mL per query.
[Sharma et al. 2026](research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md)
reconstruct Google's figure to within 2.3% from Google's own inputs and identify it as Category 2
water under ISO/IEC 30134-9, covering on-site cooling and excluding the water consumed generating
the electricity. Two components account for the range between the estimates:

- **Boundary**, about 2.8x. Adding generation water at 1.80 L/kWh gives 0.725 mL, an increase
  of 179%.
- **Prompt length**, the remainder. A long prompt at 9.2 Wh reaches 28 mL on the full boundary,
  inside Li et al.'s range. Google reports the median.

The two figures measure different quantities. Google's 2026 report derives its water number by
applying its 2024 fleetwide WUE to a May 2025 energy measurement, and publishes no WUE figure
anywhere in the document.

Water use is about 2% of US consumptive use nationally
([CRS 2026](research/water/034-crs-2026-data-centers-water-faq.md)). At individual sites the constraint is
tighter: peak-day demand at Meta's Lebanon, Indiana facility reaches 1.34x the host utility's
entire delivery capacity
([Akinade et al. 2026](research/water/033-akinade-2026-water-consumption-impact-utility-burden.md)).

### Grid and prices

PJM's statutory market monitor re-cleared the 2027/28 capacity auction with data-centre load
removed. Revenues fall from $16.41bn to $9.91bn. Data centres account for $6.50bn in that year
and $23.10bn across three auctions. Of the 17,071 MW driving the result, 13,018 MW does not yet
exist ([Monitoring Analytics 2026](research/community/016-monitoring-analytics-2026-pjm-capacity-data-center.md)).

An instrumental-variable study reaches the opposite result: a 10% rise in data-centre capacity
lowered residential rates about 0.4%, on the mechanism that durable new load spreads embedded
fixed costs ([Watten et al. 2026](research/community/018-watten-2026-data-centers-lowered-rates-iv.md)).
Two of three authors are EPRI-funded and the first-stage F statistic is 7.8, a weak instrument.
The two studies agree on the economics and differ on whether the system is supply-constrained.

Health damage falls predominantly on Scope 2 and lands away from host communities: $20.9bn and
1,262 deaths in 2028 under high growth, with over 90% attributable to generating plants
([Han et al. 2026](research/community/023-han-2026-data-center-health-costs-county.md)).

### Efficiency techniques measured in joules

Techniques validated on proxy metrics such as precision width, latency and FLOPs do not
reliably reduce energy
([Delavande et al. 2026](research/frugal/021-delavande-2026-quantization-batching-serving-energy.md),
[Dutta et al. 2026](research/frugal/022-dutta-2026-speculative-decoding-energy.md),
[Alfarizy et al. 2026](research/frugal/023-alfarizy-2026-moe-sparsity-edge-energy.md)):

- INT8 used 2 to 3x more energy than FP32 in memory-bound decode on an H100
- Speculative decoding ranged from 2.51x saving to 1.6x penalty depending on dataset
- MoE with 1.3B active parameters used 2.1x the energy per token of a dense 1B model on Jetson

Reasoning post-training cost 17x the instruction variant of the same base model on the same
cluster, 87% of it RL rollout generation. Development runs were 82.2% of total compute, so a
training figure citing only the final run understates by about 5x
([Morrison et al. 2026](research/frugal/018-morrison-2026-olmo3-reasoning-posttraining-17x.md)).
Test-time scaling multiplies per-query energy roughly 13x
([Oviedo et al. 2026](research/ghg/026-oviedo-2026-per-query-inference-energy.md)).

Published per-query figures are not comparable across studies. Task type alone swings energy 25x
and utilisation another 3 to 5x
([Chung et al. 2026](research/frugal/025-chung-2026-inference-energy-diagnosis-variance.md)).

### Avoided-emissions claims

Google attributes 41 MtCO2e of avoided emissions to "AI solutions." Google Earth accounts for
27.8 Mt of that, computed by interviewing developers about whether Earth imagery informed their
projects, then counting the full annual generation of every solar and wind plant those developers
built since 2020. The method applies no attribution fraction and no additionality test, and
reports cumulative stock as an annual flow
([Google 2026](research/narrative/022-google-2026-enabled-emissions-41mt.md)). Google's own 2025
footprint was about 14.5 Mt.

The IEA qualifies its own 1,400 Mt avoided-emissions figure: there is "currently no momentum that
could ensure the widespread adoption of these AI applications," the impact "could be marginal,"
and it "could be negated by rebound effects." Two of its five named mechanisms raise fossil-system
productivity ([IEA 2025](research/narrative/021-iea-2025-energy-and-ai-avoided-emissions-scenario.md)).

Across five avoided-emissions guidance documents, 14 methodological components appear and 2 are
common to all five
([O'Keeffe & Brander 2026](research/narrative/023-okeeffe-brander-2026-avoided-emissions-methodology-comparison.md)).

The DeepMind 40% cooling-reduction claim, from one data centre on "a typical day of testing" in
July 2016, has no independent verification, and Google's 2026 report does not restate it
([Google DeepMind 2016; Google 2026](research/narrative/024-google-2026-frozen-2008-pue-baseline-and-deepmind-claim.md)).

### Regulation

The EU AI Act's energy-documentation duty became applicable on 2 August 2025 with no measurement
standard behind it. The Bundesnetzagentur states that the Article 40(2) standards "have not yet
been delivered" ([Bundesnetzagentur 2026](research/policy/017-bnetza-2026-no-harmonised-standard-ai-energy-efficiency.md)).
The GPAI documentation form requests training energy in MWh and inference as a FLOPs count, is
not published, and permits "N/A" where a compute provider withholds data
([EC AI Office 2025](research/policy/016-ec-2025-gpai-code-of-practice-model-documentation-form.md)).

The first mandatory EU data-centre reporting round reached 36% of facilities across 770 sites,
with six member states reporting nothing. It yielded weighted PUE 1.36 and WUE 0.58 m³/MWh, with
a renewable factor of 0.87 inflated by Guarantees of Origin carrying no additionality test
([DG ENER 2025](research/policy/020-dg-ener-2025-first-eu-data-centre-reporting-round.md)).

US instruments in 2025 and 2026 govern curtailment and cost allocation. Texas SB 6, FERC's
large-load show-cause orders and Virginia's enacted package contain no energy, water or emissions
term. Every state energy- and water-disclosure bill failed to pass
([state legislative tracking 2026](research/policy/024-us-states-2026-data-centre-legislation.md)).

## Gaps in the evidence

- No operator discloses AI-specific energy or emissions. Every aggregate is inferred.
- No source publishes GW energised per year. Sources report requests, forecasts or
  leases, quantities that differ from each other by years and by gigawatts.
- No 2026 empirical work on AI rebound effects exists. Position papers only.
- No independent assessment of "water positive" pledge delivery exists. Corporate self-report only.
- No independent verification of Google's 0.26 mL exists beyond reconstruction from Google's
  own inputs.
- No study quantifies whether clean generation or interconnection capacity allocated to AI
  displaces electrification. The opportunity-cost argument is unevidenced in both directions.
- No credible evidence exists on data-centre effects on property values in either direction.
- No 2026 regulatory or advertising-standards action against a named technology company over AI
  or data-centre environmental claims was found.

## Method

Searches run against OpenAlex, arXiv, Serper, and direct retrieval of agency and corporate
documents. Templates in [`/skills/`](skills/); retrieval notes for blocked sources in
[`skills/primary-sources.md`](skills/primary-sources.md).

Every excerpt states the system boundary its numbers were computed on, distinguishes measurement
from estimate from projection, and records funding and affiliation. Searches returning nothing
are logged in [`research/_log.md`](research/_log.md).

```
/research/<topic>/
  README.md                  # folder summary: established figures, caveats, gaps
  _index.md                  # scannable table of every excerpt
  NNN-author-year-topic.md   # one source, one file
```

Each topic folder opens on its own summary. Start there:
[ghg](research/ghg/), [water](research/water/), [datacenters](research/datacenters/),
[washing](research/washing/), [policy](research/policy/), [frugal](research/frugal/),
[community](research/community/), [narrative](research/narrative/).

## Stance

Claims are checked against the documents underlying them, including claims whose conclusions
support the corpus's critical framing. Two examples. The assertion that embodied emissions exceed
operational does not survive first-party accelerator data
([Schneider et al. 2025](research/ghg/027-schneider-2025-tpu-lifecycle-embodied-emissions.md)).
The widely-repeated "data-centre cancellations quadrupled in 2025" traces to an unpublished
equity-research note with no stated methodology
([Data Center Watch 2026](research/community/021-data-center-watch-2026-opposition-tracking.md)).

Where a company's position has merit, the excerpt records it beside the critique.

See [RESEARCH_PLAN.md](RESEARCH_PLAN.md) for open questions and [CLAUDE.md](CLAUDE.md) for the
rules excerpts are written under.
