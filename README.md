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
| [Water](research/water/) | Cooling, per-query estimates, on-site vs off-site boundaries | 35 |
| [Data centres](research/datacenters/) | Buildout, interconnection, power sourcing, efficiency metrics | 25 |
| [Greenwashing](research/washing/) | Claim versus underlying disclosure, by named company | 25 |
| [Policy](research/policy/) | AI Act, EED Article 12, US state and federal instruments | 23 |
| [Frugal AI](research/frugal/) | Measured efficiency, and where efficiency reverses sign | 26 |
| [Grid and community](research/community/) | Prices, cost allocation, siting, environmental justice | 24 |
| [AI-for-climate narrative](research/narrative/) | Avoided-emissions claims and their counterfactuals | 28 |

## What the corpus establishes

### Aggregate energy and emissions

Data centres consumed 415 TWh in 2024, about 1.5% of global electricity, rising to roughly
945 TWh by 2030 on the IEA's base case ([IEA 2025](research/ghg/023-iea-2025-energy-and-ai-datacentre-electricity.md)).
US data centres used 192 TWh in 2024, 4.7% of national electricity, with a 2030 reference case
of 649 TWh and a compounded range of 521–843 TWh
([LBNL 2026](research/datacenters/016-lbnl-2026-us-dc-energy-2025-update.md)).

AI-attributable emissions for 2025 are estimated at **32.6–79.7 MtCO2, operational only**
([de Vries-Gao 2025](research/ghg/022-de-vries-gao-2025-ai-carbon-water-footprint.md)). The range
matters: its floor is 2.4x below its ceiling, it excludes manufacturing, and it is a model built
on the IEA's model, which rests on proprietary datasets that cannot be independently audited.

No operator discloses AI-specific emissions. This is the binding constraint on every figure above.

### The accounting gap

Every large operator reports two Scope 2 numbers. The headline claims rest on the market-based
one; physical grid emissions track the location-based one. From company filings:

| Company | Market-based Scope 2 | Location-based | Ratio |
|---------|---------------------:|---------------:|------:|
| [Meta, 2024](research/washing/020-meta-2025-scope2-4394x-gap.md) | 1,358 t | 5,967,348 t | 4,394x |
| [Google, 2025](research/washing/018-google-2026-market-vs-location-based-gap.md) | 2,815,000 t | 15,148,700 t | 5.4x |
| [Microsoft, FY25](research/ghg/029-microsoft-2026-sustainability-report-fy25.md) | 2,707,428 t | 12,030,000 t | 4.4x |
| [Amazon, 2025](research/washing/022-amazon-2026-market-based-only-no-location-disclosure.md) | 3,740,000 t | not published | — |

Google reports operational emissions *falling* 2.3% in 2025 while its electricity use rose 37%;
its location-based Scope 2 rose 36.9%, tracking consumption. Its headline "58 Mt avoided" is
defined in its own endnotes as the difference between the two methods, carrying the note that the
estimate "hasn't been independently verified."

Two counterweights belong beside this. Microsoft's 10.4x increase in reported Scope 2 is a
*self-correction* — it stopped crediting non-additional certificates and said so
([Microsoft 2026](research/washing/017-microsoft-2026-unbundled-rec-withdrawal.md)). And the gap
is arithmetic, not necessarily deception: annual volumetric matching produces it mechanically.
Independent attribution of 403 US hyperscale sites to actual generating plants gives
**545 gCO2/kWh, 48% above the US grid average**
([Guidi et al. 2026](research/ghg/030-guidi-2026-us-hyperscale-carbon-intensity.md)).

### Water: the dispute is resolved, and it decomposes

Google reports 0.26 mL per median Gemini text prompt; Li et al. estimated 10–25 mL per query.
[Sharma et al. 2026](research/water/027-sharma-2026-water-cost-of-intelligence-boundary.md)
reconstruct Google's figure to within 2.3% from Google's own inputs and identify it as Category 2
water under ISO/IEC 30134-9 — on-site cooling only, excluding the water consumed generating the
electricity. The gap has two components:

- **Boundary** accounts for ~2.8x. Adding generation water at 1.80 L/kWh gives 0.725 mL, +179%.
- **Prompt length** accounts for the rest. A long prompt at 9.2 Wh reaches 28 mL full-boundary —
  inside Li et al.'s range. Google reports the median.

Neither figure is wrong; they measure different things. Google's 2026 report derives its water
number by applying its **2024** fleetwide WUE to a May 2025 energy measurement, and publishes no
WUE figure anywhere in the document.

Nationally water use is small, locally it is not. Against ~2% of US consumptive use
([CRS 2026](research/water/034-crs-2026-data-centers-water-faq.md)), peak-day demand at
Meta's Lebanon, Indiana site reaches **1.34x the host utility's entire delivery capacity**
([Akinade et al. 2026](research/water/033-akinade-2026-water-consumption-impact-utility-burden.md)).

### Grid and prices

PJM's statutory market monitor re-cleared the 2027/28 capacity auction with data-centre load
removed: revenues fall from $16.41bn to $9.91bn. Data centres account for $6.50bn in that year
and $23.10bn across three auctions — and **13,018 MW of the 17,071 MW driving it does not yet
exist** ([Monitoring Analytics 2026](research/community/016-monitoring-analytics-2026-pjm-capacity-data-center.md)).

The counter-evidence is in the corpus too: an instrumental-variable study finds a 10% rise in
data-centre capacity *lowered* residential rates ~0.4%, on the mechanism that durable new load
spreads embedded fixed costs
([Watten et al. 2026](research/community/018-watten-2026-data-centers-lowered-rates-iv.md)).
Two of three authors are EPRI-funded and the first-stage F is weak; both are noted in the file.
The disagreement is about whether the system is supply-constrained, not about the economics.

Health damage is predominantly Scope 2 and lands away from host communities: $20.9bn and 1,262
deaths in 2028 under high growth, >90% attributable to generating plants rather than the
facilities ([Han et al. 2026](research/community/023-han-2026-data-center-health-costs-county.md)).

### Efficiency reverses sign when measured in joules

Techniques validated on proxy metrics — precision width, latency, FLOPs — do not reliably reduce
energy ([Delavande et al. 2026](research/frugal/021-delavande-2026-quantization-batching-serving-energy.md),
[Dutta et al. 2026](research/frugal/022-dutta-2026-speculative-decoding-energy.md),
[Alfarizy et al. 2026](research/frugal/023-alfarizy-2026-moe-sparsity-edge-energy.md)):

- INT8 used 2–3x **more** energy than FP32 in memory-bound decode on an H100
- Speculative decoding ranged from 2.51x saving to 1.6x penalty depending on dataset
- MoE with 1.3B active parameters used 2.1x the energy per token of a dense 1B model on Jetson

Reasoning post-training cost 17x the instruction variant of the same base model on the same
cluster, 87% of it RL rollout generation; development runs were 82.2% of total compute, so any
training figure citing only the final run understates by ~5x
([Morrison et al. 2026](research/frugal/018-morrison-2026-olmo3-reasoning-posttraining-17x.md)).
Test-time scaling multiplies per-query energy roughly 13x
([Oviedo et al. 2026](research/ghg/026-oviedo-2026-per-query-inference-energy.md)).

Published per-query figures are not comparable across studies: task type alone swings energy 25x,
utilisation another 3–5x ([Chung et al. 2026](research/frugal/025-chung-2026-inference-energy-diagnosis-variance.md)).

### Avoided-emissions claims

Google attributes 41 MtCO2e of avoided emissions to "AI solutions." **27.8 Mt of it is assigned to
Google Earth**, computed by interviewing developers about whether Earth imagery informed their
projects, then counting the full annual generation of every solar and wind plant those developers
built since 2020 — no attribution fraction, no additionality test, cumulative stock reported as
annual flow ([Google 2026](research/narrative/022-google-2026-enabled-emissions-41mt.md)).
Google's own 2025 footprint was ~14.5 Mt.

The IEA's 1,400 Mt avoided-emissions figure is qualified by the IEA itself: there is "currently no
momentum that could ensure the widespread adoption of these AI applications," the impact "could be
marginal," and it "could be negated by rebound effects." Two of its five named mechanisms raise
fossil-system productivity ([IEA 2025](research/narrative/021-iea-2025-energy-and-ai-avoided-emissions-scenario.md)).

Across five avoided-emissions guidance documents, 14 methodological components appear and only 2
are common to all five ([O'Keeffe & Brander 2026](research/narrative/023-okeeffe-brander-2026-avoided-emissions-methodology-comparison.md)).

The DeepMind 40% cooling-reduction claim — one data centre, "a typical day of testing", July 2016 —
still has no independent verification, and Google's 2026 report does not restate it
([file](research/narrative/024-google-2026-frozen-2008-pue-baseline-and-deepmind-claim.md)).

### Regulation

The EU AI Act's energy-documentation duty became applicable 2 August 2025 with no measurement
standard behind it; the Bundesnetzagentur states the Article 40(2) standards "have not yet been
delivered" ([file](research/policy/017-bnetza-2026-no-harmonised-standard-ai-energy-efficiency.md)).
The GPAI documentation form requests training energy in MWh but **inference as a FLOPs count**, is
not published, and permits "N/A" where a compute provider withholds data
([file](research/policy/016-ec-2025-gpai-code-of-practice-model-documentation-form.md)).

The first mandatory EU data-centre reporting round reached 36% of facilities — 770 sites, six
member states reporting nothing. It yielded weighted PUE 1.36 and WUE 0.58 m³/MWh, with a
renewable factor of 0.87 inflated by Guarantees of Origin carrying no additionality test
([DG ENER 2025](research/policy/020-dg-ener-2025-first-eu-data-centre-reporting-round.md)).

US instruments in 2025–26 are grid-economic, not environmental. Texas SB 6, FERC's large-load
show-cause orders and Virginia's enacted package concern curtailment and cost allocation. Every
state energy- and water-*disclosure* bill was introduced, not passed
([file](research/policy/024-us-states-2026-data-centre-legislation.md)).

## Where evidence does not exist

Recorded because absence is a finding:

- **No operator discloses AI-specific energy or emissions.** Every aggregate is inferred.
- **No source publishes GW actually energised per year.** Sources report requests, forecasts, or
  leases — quantities that differ from each other by years and gigawatts.
- **No 2026 empirical work on AI rebound effects.** Position papers only.
- **No independent assessment of "water positive" pledge delivery.** Corporate self-report only.
- **No independent verification of Google's 0.26 mL** beyond reconstruction from Google's own inputs.
- **No quantification of clean generation or interconnection capacity allocated to AI displacing
  electrification.** The opportunity-cost argument remains unevidenced in either direction.
- **No credible evidence on data-centre effects on property values**, either direction.
- **No 2026 regulatory or advertising-standards action** against a named technology company over
  AI or data-centre environmental claims.

## Method

Searches run against OpenAlex, arXiv, Serper, and direct retrieval of agency and corporate
documents. Templates in [`/skills/`](skills/); retrieval notes for blocked sources in
[`skills/primary-sources.md`](skills/primary-sources.md).

Every excerpt states the system boundary its numbers were computed on, distinguishes measurement
from estimate from projection, and records funding and affiliation. Searches returning nothing are
logged in [`research/_log.md`](research/_log.md).

```
/research/<topic>/
  _index.md                  # scannable table of the folder's excerpts
  NNN-author-year-topic.md   # one source, one file
```

## Stance

Claims are checked against the documents underlying them, including claims whose conclusions are
congenial. Two examples from this corpus: the assertion that embodied emissions exceed operational
does not survive first-party accelerator data
([Schneider et al. 2025](research/ghg/027-schneider-2025-tpu-lifecycle-embodied-emissions.md)),
and the widely-repeated "data-centre cancellations quadrupled in 2025" traces to an unpublished
equity-research note with no stated methodology
([file](research/community/021-data-center-watch-2026-opposition-tracking.md)).

Where a company's position has merit it is recorded alongside the critique.

See [RESEARCH_PLAN.md](RESEARCH_PLAN.md) for open questions and [CLAUDE.md](CLAUDE.md) for the
rules excerpts are written under.
