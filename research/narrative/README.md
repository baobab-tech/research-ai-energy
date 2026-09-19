# The "AI for Climate" Narrative

17 excerpts, every one verified against its source, examining claims that AI reduces emissions: the figures published, the counterfactuals
they rest on, and the deployment evidence behind them.

[Full index](_index.md)

## The two largest published claims

**Google: 41 MtCO2e attributed to "AI solutions."** Google Earth accounts for 27.8 Mt of it, or
68%. The method interviews developers about whether Earth imagery informed their projects "from
siting to construction," then counts the full annual generation of every solar and onshore wind
plant those developers built since 2020. No attribution fraction, no additionality test, and
cumulative stock reported as an annual flow. Every line carries the footnote "The data and claims
have not been independently verified" ([022](022-google-2026-enabled-emissions-41mt.md)). Google's
own 2025 footprint was about 14.5 Mt. Microsoft publishes no quantified AI-for-climate figure.

**IEA: 1,400 Mt.** The IEA's own text states there is "currently no momentum that could ensure
the widespread adoption of these AI applications," that the impact "could be marginal," and that
it "could be negated by rebound effects." The scenario gives no adoption rate, no counterfactual
definition and no sectoral breakdown in text, and the IEA compares data-centre emissions
against the figure without netting them from it. Two of its five named mechanisms, methane leak detection in
oil and gas and gas plant efficiency, raise fossil-system productivity
([021](021-iea-2025-energy-and-ai-avoided-emissions-scenario.md)).

## The category is not standardised

Across five avoided-emissions guidance documents, 14 methodological components appear and 2 are
common to all five. All five lack specificity on at least half of their own components, and the
single point of alignment, a life-cycle approach, still splits attributional from consequential
([023](023-okeeffe-brander-2026-avoided-emissions-methodology-comparison.md)).

Assessments also omit AI-side emissions and the lag between carbon spent now and benefit realised
later; a 3% carbon discount rate changes the conclusion
([029](029-xu-2026-time-aware-carbon-cost-of-ai-decarbonization.md)). A systematic review finds
83% of environmental studies portray AI's impact as positive, 72% cover only energy and CO2, and
11% consider rebound ([028](028-carmeno-2026-systematic-review-83-percent-positive.md)).

## Deployment evidence

**The DeepMind 40% cooling claim has never been independently verified.** One data centre, "a
typical day of testing," July 2016. The promised publication never appeared and Google's 2026
report does not mention DeepMind or restate the figure. Google's replacement efficiency claim of
2.9 Mt freezes its 2008 PUE of 1.21 for seventeen years as the counterfactual and assumes the
counterfactual energy would not have been matched with clean energy
([024](024-google-2026-frozen-2008-pue-baseline-and-deepmind-claim.md)).

**HVAC, one of the five IEA mechanisms.** Of 66 LLM-for-HVAC studies, 4 reach pilot-level
evidence and none reports sustained operational deployment
([025](025-neubauer-2026-llm-hvac-no-sustained-deployment.md)). In wastewater treatment, almost
all applications are predictive studies at small scale, with two full-scale operational digital
twins identified ([020](020-ai-wastewater-treatment-limits-2025.md)).

## The net effect may be negative

Modelled US net energy change from AI **adoption** is +2.16 quads (industry +1.25, transport
+1.12, commercial −0.22), with signs robust in 88 to 99% of Monte Carlo draws, against roughly
0.6 quads of current US data-centre electricity. The adoption side is the larger term and is
where this literature looks least ([026](026-he-2026-adoption-side-net-energy-increase.md)).

The counter-case has contract evidence: 2% of ICT sector inputs go to oil and gas, and in 2022
the ICT-to-oil-and-gas flow was more than 4x the ICT-to-renewables-and-nuclear flow. The
Microsoft–XTO Energy Permian agreement implies about 6.7 MtCO2 of added emissions in 2025 alone,
43% of Microsoft's own 2024 market-based footprint, and absent from its Scope 3
([027](027-roussilhe-2026-ict-oil-and-gas-counting-own-goals.md)).

## Where benefit claims hold

Two macro-panel results are held here, and both are weaker than their headline readings.

Technological innovation, proxied by resident patent applications, associates with a 0.33%
long-run rise in the renewable share of final energy across the G-20 over 1995 to 2022
([016](016-han-2025-technological-innovation-renewable-energy-g20.md)). No AI, computing or
data-centre variable appears in the paper.

AI, proxied by per-capita stock of industrial robots, associates with a 0.0018% fall in
ecological footprint per 1% rise, across 67 countries over 1993 to 2019
([007](007-wang-2024-ai-ecological-footprints-67-countries.md)). The energy-use control in the
same regression is roughly 90x larger. The panel ends before generative AI, and system-GMM with
internal instruments is not a causal design.

The most-cited peer-reviewed statement that AI is a "transformative catalyst" for the energy
transition reports no synthesis method, no adoption pathway and no netting of AI's own load
([011](011-wang-2025-ai-energy-transition-catalyst.md)). It is held as the canonical instance of
the claim, not as evidence for it.

The distinction that decides these claims is between a measured deployment and a modelled
association.

## Gaps

- No source quantifies whether clean generation or interconnection capacity allocated to AI
  displaces electrification. Queue data exists (8,200 projects, 2,061 GW queued, 13% of
  2000 to 2020 capacity operational) but does not speak to displacement.
- No 2026 systematic review assessing net AI climate impact end to end with the AI footprint
  netted off.
- The 4:1 adaptation-over-mitigation ratio ([018](018-ai-climate-resilience-systematic-review-2025.md))
  holds within its corpus (385 studies, one denominator, p < 0.0001), but the search string
  requires resilience terms, so it measures the composition of resilience-framed literature.
