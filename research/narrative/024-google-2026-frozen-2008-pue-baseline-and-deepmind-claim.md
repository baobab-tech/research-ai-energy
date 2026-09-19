# Google's operational avoided-emissions counterfactual freezes its 2008 PUE for seventeen years; the DeepMind 40% cooling claim has never been published or verified

**Topic:** narrative — counterfactual construction in operational efficiency claims; status of the canonical AI-cooling deployment
**Source:** Google, 2026 (*Google 2026 Environmental Report*); Google DeepMind, 2016 (blog post)
**Type:** corporate disclosure
**URL:** https://sustainability.google/files/google-2026-environmental-report.pdf
**Source note:** and https://deepmind.google/blog/deepmind-ai-reduces-google-data-centre-cooling-bill-by-40/
**Published:** 2026-06 (report); 2016-07-20 (DeepMind claim)

## Finding

Google's claim that data centre energy efficiency avoided approximately 2.9 million tCO2e in 2025 rests on a counterfactual in which its fleet-wide PUE stays at the 2008 value of 1.21 for seventeen years. The footnote states the assumption explicitly: "This baseline assumes that our PUE would have remained the same without our efficiency improvements," and adds "We assume additional energy consumption in the baseline scenario would not have been matched with additional clean energy procurement" — a second assumption that inflates the result by applying a dirtier grid factor to the counterfactual than to the actual.

Separately, the canonical AI-for-climate deployment case — DeepMind's 2016 claim of "a 40 percent reduction in the amount of energy used for cooling" and "a 15 percent reduction in overall PUE overhead" — was announced on a corporate blog, on one live data centre, with results shown for "a typical day of testing." The post promised "an upcoming publication" that describes the rollout. Ten years on, Google's 2026 Environmental Report does not mention DeepMind, does not attribute any part of its PUE performance to machine-learning cooling control, and does not restate the 40% figure. No independent verification of the claim was located.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Google fleet-wide average PUE, 2008 (baseline) | 1.21 | Earliest fleet-wide trailing-12-month PUE; used as frozen counterfactual |
| Google fleet-wide average PUE, 2025 | 1.09 | Trailing 12-month, fleet-wide; facilities reported once at "stable operations" |
| Overhead reduction, 2008→2025 | 21% → 9% of IT load, i.e. ~57% of overhead removed over 17 years | All measures combined, not attributable to any one intervention |
| Claimed avoided emissions from PUE improvement, 2025 | ~2.9 million tCO2e | Frozen 1.21 baseline, 2019–2025 compared each year; grid factor from Google's own scope 2 inventory |
| Other operational avoided-emissions line items, 2025 | software and computing efficiencies 14.1 Mt; machine hardware efficiencies (data centre) contributing to a 24.3 Mt total; data centre design and construction 2.6 Mt; supply-chain clean energy 1.2 Mt; operational clean energy 12 Mt | Each a separate counterfactual; summed to ">58 million tCO2e" |
| DeepMind 2016 claim | 40% reduction in cooling energy; 15% reduction in overall PUE overhead | One data centre; "a typical day of testing"; no baseline period, duration or facility count given |

## Methodology

Frozen-baseline counterfactual, applied to a metric (PUE) that is a ratio rather than an absolute quantity. Three structural problems follow.

First, efficiency in the sector improved industry-wide between 2008 and 2025 for reasons unrelated to any single operator — hot/cold aisle containment, higher allowed inlet temperatures under successive ASHRAE revisions, free-air and evaporative cooling, higher-voltage distribution. Holding 1.21 constant attributes all of that to Google's own action.

Second, the counterfactual is applied to a growing IT load. As Google's compute grows, the frozen-baseline gap widens mechanically, so the avoided-emissions figure rises with expansion. The metric rewards building more.

Third, PUE measures overhead relative to IT load; it falls when IT load rises faster than overhead, independent of whether cooling got better. Google's reported 1.09 is consistent with both genuine cooling improvement and rapid growth in dense AI racks.

On the DeepMind claim: 15% of overhead, applied to a fleet PUE around 1.11–1.12 in 2016, is roughly one to two points of PUE — within the total 12-point movement recorded across the entire 2008–2025 series. The claim is arithmetically possible. It is not separately identifiable in any published Google data, and Google no longer cites it.

## Limitations and conflicts

Both sources are produced by the party making the claim. The 2026 report's footnotes state for each avoided-emissions line: "The data and claims have not been independently verified." The DeepMind blog post is marketing material, not a technical report: it names no test duration, no control period, no statistical treatment, and no facility. Google has published a later peer-reviewed line of work on data centre cooling using model-predictive control, but that is a different system and does not validate the 2016 number.

Note also what is absent: the 2026 report's single case where AI's own compute cost is netted against its benefit — the contrails model, 380 tCO2e of compute against 3 000 tCO2e of contrail avoidance — is a project roughly 0.007% the size of the 41 Mt product claim. Netting is performed only where the ratio is favourable and the quantity is trivial.

## Relation to existing corpus

Complements `narrative/022-google-2026-enabled-emissions-41mt.md`, which covers the separate product-enabled 41 Mt claim from the same report. No other overlap; the DeepMind cooling claim was not present anywhere in the repository.

---
Retrieved: 2026-09-19
Search: WebSearch "DeepMind data centre cooling 40% claim independently verified"; full text extraction of the Google 2026 Environmental Report PDF, endnotes 148–153
