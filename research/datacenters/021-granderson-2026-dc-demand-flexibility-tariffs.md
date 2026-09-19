# Fewer than one in five proposed US power projects reaches operation; LBNL argues data-centre demand flexibility is the bridge, and names the tariffs where operators already accept forced curtailment

**Topic:** Data-centre infrastructure — grid-interactive load, curtailment tolerance, buildout attrition
**Source:** Granderson, J., Hoffman, I., Holecek, B., Crowe, E., Smith, S., Mims Frick, N. — Lawrence Berkeley National Laboratory, 2026. Published in National Academy of Engineering, *The Bridge* 56(1), Spring 2026 issue on AI-Driven Data Centers
**Type:** agency report (national laboratory, in a peer-edited NAE issue)
**URL:** https://eta-publications.lbl.gov/sites/default/files/2026-07/integrading_ai_data_centers_with_the_power_grid.pdf
**Source note:** DOI 10.20357/B7X61S
**Published:** 2026-05

## Finding

The paper supplies the attrition statistic that most buildout reporting omits: recently, fewer than one in five proposed US power projects has become operational (citing Rand et al. 2025). Against that, more than 700 new gas-fired plants totalling 260 GW are queued — a 270% increase since 2022 — which would grow the 550 GW US gas fleet by over half at a build cost exceeding $400 billion. The authors' argument is that flexibility, not generation, is the faster path, and they document that some utilities have already made curtailment mandatory rather than voluntary: Idaho Power requires certain customers to permit remote disconnection for up to ten hours per event and up to 225 hours per year. That is a concrete answer to whether operators accept curtailment — under some tariffs they have no choice, and they take the tariff.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Proposed US power projects reaching operation | fewer than 1 in 5, recently | Rand et al. 2025, cited |
| US power projects awaiting approval | nearly 9,000 | Rand et al. 2025 |
| Queued new gas plants | >700 plants, 260 GW | Interconnection.fyi 2026; +270% since 2022 |
| Existing US gas fleet | 550 GW; could grow >50% | GEM 2026 |
| Gas build-out cost if delivered | >$400 billion | GEM 2026; GridLab et al. 2025 |
| Idaho Power mandatory curtailment | up to 10 h per interruption event; up to 225 h/year | Idaho Power Company 2024 tariff |
| Black Hills Energy | large-power customers must run own backup generation during peaks, for lower rates | Black Hills Energy 2020 |
| Alliant Energy / Evergy Kansas Central | voluntary interruptible service riders; $/kW credit, penalty for non-compliance | 2023–2025 tariffs |
| New large-load tariffs in 2025 | at least one approved or proposed every month | Frick and Lam 2025 |
| Data-centre projects blocked or delayed by public opposition since 2023 | >$100 billion | Data Center Watch 2025 |
| IT equipment share of data-centre cost | upwards of three-quarters | — |

## Methodology

Review and synthesis, not new measurement. The flexibility taxonomy has four strands: computational load flexibility (temporal shifting of delay-tolerant training, spatial shifting between facilities, intensity throttling), core facility infrastructure flexibility (cooling setpoints within ASHRAE 2024 short-term "allowable" ranges; UPS batteries providing grid support), energy storage, and on-site generation. The authors argue behind-the-meter storage and generation strategies carry the lowest operational risk because they do not alter workloads, at the cost of capital, space and interconnection planning.

On motivation, the paper is blunt that conventional demand-response economics do not move hyperscalers: because IT equipment is over three-quarters of cost, "traditional incentives from the power sector such as demand flexibility credits or reduced electricity charges, are less compelling." What does move them is time-to-energisation — hence PG&E and Portland General Electric programmes that connect customers before full capacity upgrades complete, in exchange for flexibility — plus statutory mandates such as Texas SB6, and public acceptance.

## Limitations and conflicts

Supported by DOE's Office of Critical Minerals and Energy Innovation under Contract DE-AC02-05CH11231. Much of the evidence for flexibility in practice is drawn from industry self-reports the authors name as such: Google's utility pilots in Tennessee, Indiana, Michigan and Nebraska, EmeraldAI's demonstration in Arizona Public Service territory, and Verrus's published design approach. These are demonstrations and vendor publications, not independently verified programme results, and the paper does not report megawatt-hours actually curtailed by any hyperscaler. The mandatory-curtailment examples (Idaho Power, Black Hills) are small-utility tariffs applying to industrial customers generally, not evidence that hyperscale AI campuses have signed them. The "$100 billion blocked or delayed" figure comes from Data Center Watch, an advocacy tracker, and is not audited. Figure 1 uses the 2024 Shehabi et al. demand curve; LBNL's June 2026 update revises those figures (016).

## Relation to existing corpus

No direct overlap — the folder had no demand-flexibility or tariff material. The one-in-five completion rate is the general-case version of the ERCOT-specific attrition in `017-ercot-2026-large-load-queue-474gw.md`. Contrasts with `013-rollinson-2025-offgrid-hyperscale-feasibility.md`, which argues for leaving the grid entirely; this paper argues the grid is served better by staying on it flexibly.

---
Retrieved: 2026-09-19
Search: Serper "data center flexible load curtailment 2026 study Norris Duke Nicholas Institute" → LBNL ETA publications PDF, text extracted locally
