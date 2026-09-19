# Large-load tariffs went from 41 to 104 in twelve months, with a median ~50 MW threshold, 10-20 year terms and ~80% minimum-take obligations

**Topic:** Cost allocation — the design of the tariffs meant to stop data-centre costs shifting onto other ratepayers, and their coverage
**Source:** Smart Electric Power Alliance (SEPA) and NC Clean Energy Technology Center (NCCETC), Database of Emerging Large-Load Tariffs (DELTa); analyses by Lindemann and Collier (DSIRE Insight, Sep 2026) and CoBank (Apr 2026)
**Type:** dataset with published analyses
**URL:** https://www.dsireinsight.com/blog/2026/9/1/stretching-the-possibilities-where-large-load-tariffs-fit-in-the-future-of-data-center-flexibility
**Source note:** https://www.cobank.com/knowledge-exchange/the-state-of-large-load-rate-design-insights-from-the-delta-database
**Published:** 2026-09-01 (DSIRE Insight analysis, data to July 2026); 2026-04-30 (CoBank analysis, data to 31 March 2026)
**Note on the database URL:** the DELTa landing page at sepapower.org/large-load-tariffs-database/ returns HTTP 403 to automated requests and was not directly verified; both analyses above were retrieved in full.

## Finding

DELTa tracked 104 approved and pending large-load tariffs and service rules across more than 70 utilities in 37 states as of July 2026, up from 41 a year earlier and from 14 total over 2018-2024. The standard design bundles three protections: a high demand threshold (45 percent of tariffs set it at 50 MW or above), a long minimum term (most 10-20 years, with Florida Power & Light and Kentucky Power at 20 years against a 1-3 year commercial norm), and a minimum-take obligation averaging around 80 percent of contracted capacity. Collateral appears in 44 of 77 filings reviewed at the March 2026 snapshot, with Dominion requiring $1.5 million per MW. Only one quarter of tariffs contain any concrete flexibility or curtailment pathway.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Tariffs tracked, July 2026 | 104 (69 approved, 35 proposed) | 70+ utilities, 37 states |
| Tariffs tracked, July 2025 | 41 | Same database, prior snapshot |
| Tariffs 2018-2024 (whole period) | 14 | Versus 20 approved in 2024 alone and 53 proposed or approved in 2025 |
| March 2026 snapshot | 77 filings, 60 utilities (51 approved, 26 proposed) | Basis of the CoBank tariff-design statistics below |
| Threshold | 45% set at >=50 MW; average minimum demand ~50 MW; range 1 MW to 500 MW; ~three quarters target >20 MW | |
| Minimum contract term | Mostly 10-20 years; FPL and Kentucky Power 20 years | Commercial baseline 1-3 years |
| Minimum take / minimum bill | ~80% of contracted capacity on average; range 70-100% of monthly billing; Consumers Energy 80%, Kentucky Power 90% | |
| Collateral | 44 of 77 filings; Dominion $1.5m/MW with 70% exemption for credit-rated customers; Michigan collateral = half the exit fee | |
| Flexibility/curtailment provisions | 25% of tariffs | Interruptible riders, BTM generation dispatch, DR, emergency load response, non-firm interconnection |

## Methodology

DELTa is a curated register of filed tariff documents, updated quarterly, covering investor-owned utilities plus selected public power, cooperative and G&T utilities. The counts are of filings, not of MW covered or of customers served, so they measure regulatory activity rather than the share of data-centre load actually subject to a protective tariff — a distinction that matters, since existing contracts are generally grandfathered.

The design statistics (contract term, minimum take, collateral) come from the CoBank analysis of the 31 March 2026 snapshot; the counts and flexibility statistics from the September 2026 DSIRE Insight analysis of the July 2026 snapshot. The two are different vintages of the same database and should not be mixed within a single sentence.

## Limitations and conflicts

SEPA is a utility-and-vendor membership organisation; NCCETC is a state-university-hosted clean-energy centre; the CoBank analysis is published by a cooperative bank whose borrowers include electric cooperatives serving large loads. None is a neutral party, though the underlying object — filed tariff text — is verifiable.

What the database cannot show: whether the minimum-take and collateral terms are sufficient to cover the stranded-asset exposure they are designed for. A 20-year term with an 80 percent minimum take still leaves the utility and its other ratepayers exposed if the counterparty's credit deteriorates, and $1.5m/MW of collateral is small against the cost of a dedicated generation and transmission build. The database also does not record how many of these tariffs have been applied to an actual signed contract.

## Relation to existing corpus

No direct overlap. Provides the national distribution against which the single-state order in /Users/olivier/DEV/research-ai-energy/research/community/019-pa-puc-2026-large-load-but-for-tariff.md can be placed.

---
Retrieved: 2026-09-19
Search: WebSearch "2026 state public utility commission order large load tariff data center minimum take contract stranded cost" and "SEPA NCCETC DELTa Database Emerging Large-Load Tariffs 2026 report"
