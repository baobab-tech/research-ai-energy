# Research Plan: AI Environmental Impact

## Research Stance

**Critical lens**: Scrutinize corporate claims, identify greenwashing/bluewashing, demand verifiable numbers with sources.

**Key questions**:
- What are the actual numbers vs. what companies report?
- Who funds the studies? What are the conflicts of interest?
- What's being hidden or obscured?
- How do estimates vary and why?

**Time Period:** 2024-2026 (prioritize 2025-2026)

**Priority Sources:**
1. Academic papers via OpenAlex (primary)
2. arXiv preprints
3. Web/news via Serper (secondary)

## Current Landscape (Jan 2026)

- **Data center backlash**: Project cancellations quadrupled in 2025 as communities push back
- **Grid strain**: States examining whether AI data centers are increasing electricity bills
- **Water uncertainty**: Wildly conflicting estimates ("depends on whom you ask")
- **Scale**: 2025 AI GHG footprint estimated at ~80M tonnes CO2e (comparable to NYC)
- **Greenwashing**: "100% renewable" claims vs actual grid mix reality
- **Bluewashing**: "Water positive" pledges vs local aquifer depletion
- **Transparency gaps**: Providers refuse to disclose per-query costs

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
- Data center project cancellations (2025 surge)
- Environmental justice concerns
- Community organizing tactics

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

## Progress Tracking

### GHG Emissions
- [ ] Training emissions
- [ ] Inference emissions
- [ ] Lifecycle/embodied
- [ ] Numbers compilation

### Water
- [ ] Direct consumption
- [ ] Reuse/recycling
- [ ] "Water positive" scrutiny
- [ ] Numbers compilation

### Data Centers
- [ ] Infrastructure growth
- [ ] Power sources
- [ ] Efficiency metrics

### Greenwashing/Bluewashing
- [ ] Corporate claims audit
- [ ] Reporting gaps
- [ ] Verification analysis

### Policy
- [ ] Current regulation
- [ ] Proposed policies
- [ ] Self-regulation review

### Community
- [ ] Local opposition
- [ ] Grid/ratepayer impact

### Frugal AI
- [ ] Efficient architectures
- [ ] Optimization techniques
- [ ] When NOT to use AI

### Narrative
- [ ] "AI for climate" claims scrutiny
- [ ] Net impact debate
