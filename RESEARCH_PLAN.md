# Research Plan: AI Environmental Impact

## Research Stance

**Critical lens**: Scrutinize corporate claims, identify greenwashing/bluewashing, demand verifiable numbers with sources.

**Key questions**:
- What are the actual numbers vs. what companies report?
- Who funds the studies? What are the conflicts of interest?
- What's being hidden or obscured?
- How do estimates vary and why?

**Time Period:** 2024-2026 (prioritize 2025-2026)

**Priority Sources** (revised 2026-09-19; full hierarchy in CLAUDE.md):
1. Measurement from instrumented production systems
2. Agency and statutory data: IEA, LBNL, EIA, EPRI, grid operators, PUC and FERC filings
3. Peer-reviewed papers and preprints via OpenAlex and arXiv
4. Corporate disclosures, as primary evidence of what is claimed, never as neutral fact
5. Journalism only to reach a document otherwise unavailable

## Current Landscape (September 2026)

Evidence for each item is in the topic folder named. Claims that could not be sourced are marked.

- **Aggregate load**: data centres 415 TWh globally in 2024 (1.5%), ~945 TWh by 2030 (IEA);
  US 192 TWh in 2024 (4.7%), 649 TWh reference case for 2030 (LBNL 2026).
- **AI emissions**: 32.6-79.7 MtCO2 for 2025, operational only (de Vries-Gao). No operator
  discloses AI-specific emissions; every aggregate is inferred.
- **Accounting gap**: market-based vs location-based Scope 2 diverges by 4.4x (Microsoft) to
  4,394x (Meta). Amazon publishes no location-based figure. Independent plant attribution puts
  hyperscale carbon intensity 48% above the US grid average.
- **Water**: the 0.26 mL vs 10-25 mL dispute decomposes into system boundary (~2.8x) and prompt
  length (the remainder). Nationally ~2% of US consumptive use; locally up to 1.34x a host
  utility's entire delivery capacity on a peak day.
- **Grid economics**: PJM's market monitor attributes $6.50bn of one capacity auction to
  data-centre load, 76% of it forecast load. Counter-evidence exists
  (IV study finding rates fell); the disagreement is about supply constraints.
- **Interconnection**: ERCOT holds ~474 GW of large-load requests, roughly 5x its system peak.
  No source publishes GW actually energised per year.
- **Regulation**: the EU AI Act energy duty is applicable and has no measurement standard behind
  it; the GPAI form records inference as a FLOPs count. US instruments govern curtailment and cost
  allocation. Every US state energy and water disclosure bill failed to pass.
- **Avoided-emissions claims**: Google's 41 Mt figure is 68% Google Earth, computed without an
  attribution fraction or additionality test. The IEA's 1,400 Mt scenario is qualified by the
  IEA's own text.
- **Community opposition**: the widely-cited "cancellations quadrupled in 2025" traces to an
  unpublished equity-research note with no stated methodology or definition, and is marked
  unsupported. The main opposition tracker has no denominator and is run by a vendor to AI
  companies.

## Research Areas

### 1. Greenhouse Gas Emissions (`/research/ghg/`)

#### 1.1 Training Emissions
- GHG cost of training large models (GPT-4, Claude, Llama, Gemini)
- CO2, methane, and other GHG breakdown
- Comparison of published estimates (who says what, and why do they differ?)

#### 1.2 Inference Emissions
- Per-query GHG estimates (with confidence intervals)
- Scaling: what happens at billions of queries/day?
- Hidden costs: model routing, failed requests, redundancy

#### 1.3 Lifecycle & Embodied Emissions
- Hardware manufacturing (GPUs, servers, networking)
- E-waste and disposal
- Rare earth mining impacts

#### 1.4 Actual Numbers
- Collect and compare ALL published estimates
- Track methodology differences
- Flag unrealistic or unsubstantiated claims

### 2. Water Consumption (`/research/water/`)

#### 2.1 Direct Water Use
- Cooling systems: evaporative vs closed-loop vs air-cooled
- Per-query water estimates (the "bottle of water per query" claims)
- Regional variations and water stress zones

#### 2.2 Water Reuse & Recycling
- Actual reuse rates vs claims
- Wastewater treatment and discharge
- Impact on local water systems

#### 2.3 "Water Positive" Claims
- What does "water positive" actually mean?
- Offset schemes vs actual reduction
- Bluewashing tactics and scrutiny

#### 2.4 Actual Numbers
- Liters per query estimates (range and methodology)
- Annual consumption by provider (where disclosed)
- Comparison to other industries

### 3. Data Centers (`/research/datacenters/`)

#### 3.1 Infrastructure Growth
- New construction pipeline
- Geographic distribution (why there?)
- Grid capacity and strain

#### 3.2 Power Sources
- "100% renewable" claims vs grid reality
- PPAs vs actual electrons consumed
- Nuclear deals (Amazon, Google, Microsoft)

#### 3.3 Efficiency Metrics
- PUE trends (and why PUE is misleading)
- WUE (Water Usage Effectiveness)
- Carbon intensity by region

### 4. Greenwashing & Bluewashing (`/research/washing/`)

#### 4.1 Corporate Sustainability Claims
- "Carbon neutral" - what it actually means
- "100% renewable energy" - the PPA shell game
- "Water positive by 2030" - offset schemes

#### 4.2 Reporting Gaps
- What's disclosed vs what's hidden
- Scope 1, 2, 3 emissions games
- Cherry-picked metrics

#### 4.3 Third-Party Verification
- Who audits these claims?
- Conflicts of interest
- Standards and their weaknesses

### 5. Policy & Regulation (`/research/policy/`)

#### 5.1 Current Regulation
- EU AI Act environmental provisions
- US state-level actions (California, Virginia)
- Disclosure requirements

#### 5.2 Proposed Policies
- Mandatory reporting proposals
- Carbon pricing for AI
- Water usage restrictions

#### 5.3 Industry Self-Regulation
- Voluntary commitments (and their track record)
- Industry consortiums
- Standards bodies

### 6. Community & Grid Impact (`/research/community/`)

#### 6.1 Local Opposition
- Project cancellations: needs a source with a stated methodology and a denominator
- Environmental justice: siting against income, race, existing pollution burden
- Community organizing tactics and outcomes (moratoria, rezoning denials, referenda)

#### 6.2 Electricity Prices & Grid
- Impact on residential electricity rates
- Grid reliability concerns
- Who pays for infrastructure upgrades?

### 7. Frugal AI (`/research/frugal/`)

#### 7.1 Efficient Architectures
- Small language models (SLMs)
- Model distillation and compression
- Sparse models and mixture of experts

#### 7.2 Inference Optimization
- Quantization
- Pruning
- Edge deployment

#### 7.3 When NOT to Use AI
- Task-appropriate model selection
- Traditional methods vs AI overkill
- The carbon cost of AI hype

#### 7.4 Research & Initiatives
- Green AI movement
- Carbon-aware computing
- Efficiency benchmarks (beyond just accuracy)

### 8. The "AI for Climate" Narrative (`/research/narrative/`)

#### 8.1 Efficiency Claims - Scrutinized
- "AI will save X tonnes of CO2" - source and methodology?
- Who funds these studies?
- Rebound effects and Jevons paradox

#### 8.2 Net Impact Debate
- Problem vs solution framing
- Actual lifecycle assessments
- Opportunity cost: what else could that energy power?

## Folder Structure

```
/research/
  /ghg/
  /water/
  /datacenters/
  /washing/
  /policy/
  /community/
  /frugal/
  /narrative/
```

## Key Search Terms

### GHG Emissions
- "AI carbon footprint", "LLM greenhouse gas emissions", "AI CO2 emissions"
- "training emissions GPT", "inference carbon cost"
- "AI environmental impact", "machine learning emissions"

### Water
- "AI water consumption", "data center water usage", "ChatGPT water footprint"
- "water positive data center", "AI water stress", "cooling water AI"
- "water reuse data center", "evaporative cooling AI"

### Greenwashing
- "AI greenwashing", "data center renewable energy claims"
- "carbon neutral AI", "tech sustainability claims"
- "PPA renewable energy criticism"

### Frugal AI
- "frugal AI", "green AI", "efficient machine learning"
- "small language models", "model compression energy"
- "sustainable AI", "carbon-aware computing"

### Policy
- "AI regulation environment", "data center regulation"
- "AI disclosure requirements", "tech emissions reporting"

## Sub-Agent Tasks

1. **ghg-training** - Training emissions estimates and comparison
2. **ghg-inference** - Per-query emissions analysis
3. **ghg-lifecycle** - Embodied emissions and hardware
4. **ghg-numbers** - Collect ALL published estimates
5. **water-direct** - Direct water consumption data
6. **water-reuse** - Reuse/recycling practices
7. **water-claims** - Scrutinize "water positive" claims
8. **water-numbers** - Collect ALL water estimates
9. **datacenter-growth** - Infrastructure expansion tracking
10. **datacenter-power** - Power source claims vs reality
11. **washing-claims** - Document greenwashing/bluewashing
12. **washing-gaps** - Identify reporting gaps
13. **policy-current** - Current regulation landscape
14. **policy-proposed** - Upcoming policy proposals
15. **community-opposition** - Local resistance documentation
16. **community-grid** - Grid and ratepayer impacts
17. **frugal-architectures** - Efficient AI approaches
18. **frugal-when-not** - When AI is overkill
19. **narrative-claims** - Scrutinize "AI for climate" claims
20. **narrative-net** - Net impact analysis

## Open Questions

Answered questions have moved to the topic indexes. These remain.

### Unevidenced in either direction
- GW actually energised per year. Every source reports requests, forecasts, or leases.
- AI rebound effects. Position papers only; no 2026 empirical work.
- Opportunity cost: whether clean generation or interconnection allocated to AI displaces
  electrification of heat, transport, industry.
- Data-centre effects on property values.
- Delivery against "water positive" pledges, assessed independently.

### Blocked on disclosure
- AI-specific energy and emissions. No operator publishes them.
- Foundry-level emission factors per wafer. No primary disclosure at that granularity.
- NVIDIA accelerator lifecycle assessment. No equivalent to Google's TPU LCA exists.
- Facility-level EU data under Article 12, legally confidential.

### Retrievable but not yet retrieved
- Privette, Barros & Cai, *AGU Advances* 2026. Wiley blocks automated access.
- FERC order text and RTO compliance filings due 17 Aug 2026. ferc.gov blocks retrieval.
- Oregon PUC Order 26-154 (UM 2377), the first implementation of the 2025 POWER Act.
- E3 May 2026 rate-decomposition report; EDGI July 2026 air-pollution analysis.
- MLPerf Power v6.0/v6.1 raw submission tables, unnormalised to joules per token.

### Methodological
- Whether reservoir evaporation should be allocated to hydropower. This single convention moves
  the indirect:direct water multiplier from 1.7:1 to 12:1 and can reverse regional rankings 94-fold.
- Marginal versus average emissions for added data-centre load. Current attribution is average only.
- Agentic and multi-turn workloads. Unmeasured; existing studies exclude tool calling.
