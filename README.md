# AI Environmental Impact Research

A critical investigation into the environmental footprint of AI systems: greenhouse gas emissions, water consumption, and the gap between corporate claims and reality.

## Why This Matters

The AI industry is growing rapidly, but its environmental costs are often hidden or downplayed:

- **Scale**: AI's 2025 GHG footprint is estimated at ~80 million tonnes CO2e (comparable to New York City)
- **Water**: GPT-3 training consumed ~700,000 liters; ChatGPT uses 10-25ml per query
- **Growth**: Global AI water demand projected at 4.2-6.6 billion m³ by 2027
- **Greenwashing**: "100% renewable" and "water positive" claims often don't match reality

## Research Areas

| Topic | Focus | Excerpts |
|-------|-------|----------|
| [GHG Emissions](research/ghg/) | Training, inference, and lifecycle carbon footprint | 21 |
| [Water Consumption](research/water/) | Cooling systems, per-query estimates, regional impacts | 26 |
| [Data Centers](research/datacenters/) | Infrastructure growth, power sources, efficiency | 15 |
| [Greenwashing](research/washing/) | Corporate claims vs reality, reporting gaps | 16 |
| [Policy](research/policy/) | Regulation, disclosure requirements, carbon pricing | 14 |
| [Frugal AI](research/frugal/) | Efficient architectures, hardware, when NOT to use AI | 16 |
| [Community Impact](research/community/) | Local opposition, grid strain, environmental justice | 15 |
| [AI-for-Climate Narrative](research/narrative/) | Scrutinizing "AI will save the planet" claims | 20 |

## Key Findings

**On emissions:**
- Efficiency gains are real (50-115% energy savings possible) but overwhelmed by demand growth
- "Efficiency is not enough" - Jevons paradox applies to AI
- Inference now dominates operational footprint as GenAI scales

**On water:**
- Google claims 0.26ml/prompt; independent research estimates 10-25ml/query (40-100x gap)
- High-power AI chips physically require liquid cooling - water use is structural
- 40% of servers remain in small/midsize data centers with worse efficiency

**On greenwashing:**
- Greenwashing is systemic (institutional pressures), not individual bad behavior
- 9% of corporate emissions targets fail, 31% quietly disappear - only 3 get media coverage
- Voluntary disclosure associated with MORE greenwashing, not less

**On the "AI for climate" narrative:**
- AI climate research focuses 4:1 on adaptation over mitigation
- Most "AI for environment" applications remain studies, not deployments
- Benefits are projected; costs are measured

## Critical Stance

This research applies scrutiny to all claims:
- **Who funded the study?** Industry-funded research is flagged
- **What's the methodology?** Especially for emissions estimates
- **What's missing?** Corporate reports often omit inconvenient data
- **Self-reported vs independent?** Google's water numbers vs Li et al.

## Sources

Primary sources are peer-reviewed academic papers (2023-2025) via:
- OpenAlex (240M+ academic papers)
- arXiv preprints
- Select news/reports for current events

Every excerpt includes a source URL.

---

## How It Works

This repository collects research excerpts - each one a single insight from a single source, saved as a markdown file with full citation.

```
/research/
  /ghg/
    _index.md              # Quick-reference index
    001-author-year-topic.md
    002-author-year-topic.md
    ...
  /water/
  /washing/
  ...
```

Each topic folder has an `_index.md` summarizing all excerpts. Browse by topic or search across all findings.

See [RESEARCH_PLAN.md](RESEARCH_PLAN.md) for the full research framework and methodology.
