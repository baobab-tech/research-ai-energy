# Modelled net energy change from deploying AI in US industry and freight is +2.16 quads, several times US data-centre electricity

**Topic:** narrative — rebound and induced demand; does AI adoption reduce energy where it is applied?
**Source:** Wei He, Daoping Wang, Hanqi Yan, Yang Wang, Sai Gu, 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2607.04016
**Published:** 2026-07-04

## Finding

The claim that AI saves energy in the sectors where it is applied does not survive sector disaggregation. Mapping occupation-level AI exposure onto US sector energy use and decomposing supply and demand effects, the authors find divergent signs: commercial buildings save 0.22 quads, while industry (+1.25 Q) and transport (+1.12 Q) increase, each sign robust across 88–99% of Monte Carlo parameter draws. The aggregate induced change is +2.16 Q (90% range +0.52 to +4.12; +1.1 Q under a conservative price-channel conversion of the rebound anchors), against roughly 0.6 Q of current US data-centre electricity. If the result holds, the adoption side of AI's energy footprint is several times larger than the compute side that energy planning currently tracks, and it points the opposite way from the avoided-emissions narrative.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| US adoption-side energy envelope, theoretical | 12.1 Q | Operational energy *exposed* to AI — scope, not consumption; electricity + gas + petroleum + process fuels |
| US adoption-side envelope, observed | ~1.4 Q | Current observed AI exposure |
| Net induced energy change at full adoption | +2.16 Q (90% MC range +0.52 to +4.12) | Joint supply–demand decomposition |
| Same, conservative price-channel conversion | +1.1 Q | Alternative rebound-anchor conversion |
| Commercial sector | −0.22 Q (saving) | Sign robust in 88–99% of draws |
| Industrial sector | +1.25 Q | Sign robust in 88–99% of draws |
| Transport sector | +1.12 Q | Sign robust in 88–99% of draws |
| Current US data-centre electricity, for comparison | ~0.6 Q | 1 Q ≈ 293 TWh |
| UK transfer | 1.9 Q envelope out of 3.7 Q national total | Same method applied to UK occupational/energy mix |

## Methodology

Modelled, not measured. Occupation-level AI exposure indices are mapped onto sector energy end-use, then a Monte Carlo joint supply–demand decomposition estimates each sector's net energy change. "Envelope" and "net change" are distinct quantities and the paper is careful about this: the 12.1 Q envelope measures how much operational energy sits in tasks AI can touch, not how much energy is consumed or saved. The +2.16 Q is the decomposed net, at full adoption — a scenario, not a forecast, and the paper does not give an adoption timeline.

The rebound mechanism is the demand-side half of the decomposition: AI lowers the effective cost of an activity (freight movement, industrial throughput), demand for that activity rises, and the increase outweighs the per-unit efficiency gain. The commercial-sector saving survives because commercial building energy is largely conditioning load with little demand elasticity to task cost; industrial and freight energy is production-linked and elastic.

Geographic result: industrial- and freight-heavy states (Texas, Louisiana, Indiana) carry the increase; commercial-dominated jurisdictions (New York, Massachusetts, DC) see substantially smaller net changes.

## Limitations and conflicts

Preprint, not peer reviewed. The chain — occupational AI-exposure index → task shift → sector energy → elasticity-driven rebound — has several joints where an assumption substitutes for an observation, and the authors' own remedy ("requiring end-use energy surveys to track AI deployment") concedes that the data to test it does not exist. The "rebound anchors" are parameters imported from the efficiency-rebound literature rather than estimated from AI deployments, and the spread between the headline +2.16 Q and the conservative +1.1 Q is a direct measure of how much rests on that choice. The 90% MC range spans nearly an order of magnitude at the low end. No funding statement is present in the preprint metadata. Treat the sign and the order-of-magnitude comparison with data-centre load as the finding; treat the point estimate as soft.

## Relation to existing corpus

No direct overlap with the narrative folder. Supplies quantitative rebound evidence of the kind that `ghg/013-tomlinson-2024-ai-vs-human-emissions-comparison.md` flags as a caveat but does not quantify, and contradicts the direction of `narrative/007-wang-2024-ai-ecological-footprints-67-countries.md` and `narrative/011-wang-2025-ai-energy-transition-catalyst.md`.

---
Retrieved: 2026-09-19
Search: WebSearch "IEA Energy and AI avoided emissions"; followed to arXiv 2607.04016, metadata confirmed via arXiv API
