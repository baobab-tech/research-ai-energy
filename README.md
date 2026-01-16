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
- Efficiency gains are real (50-115% energy savings possible) but overwhelmed by demand growth ([Verdecchia 2023](research/ghg/016-verdecchia-2023-green-ai-systematic-review-savings.md))
- "Efficiency is not enough" - Jevons paradox applies to AI ([Wright 2025](research/ghg/018-wright-2025-efficiency-not-enough.md))
- Inference now dominates operational footprint as GenAI scales ([Berthelot 2025](research/ghg/006-berthelot-2025-environmental-impact-genai-services.md))

**On water:**
- Google claims 0.26ml/prompt ([Google 2025](research/water/017-google-2025-gemini-water-measurements.md)); independent research estimates 10-25ml/query ([Li 2025](research/water/018-li-2025-cacm-ai-water-projections.md)) - a 40-100x gap
- High-power AI chips physically require liquid cooling - water use is structural ([Li & Zhu 2025](research/water/025-li-zhu-2025-data-center-liquid-cooling-review.md))
- 40% of servers remain in small/midsize data centers with worse efficiency ([Lei 2025](research/water/022-lei-2025-us-midsize-data-centers-wue.md))

**On greenwashing:**
- Greenwashing is systemic (institutional pressures), not individual bad behavior ([Forliano 2025](research/washing/012-forliano-2025-greenwashing-landscape.md))
- 9% of corporate emissions targets fail, 31% quietly disappear - only 3 get media coverage ([Jiang 2025](research/washing/009-jiang-2025-emissions-target-accountability.md))
- Voluntary disclosure associated with MORE greenwashing, not less ([Bingler 2024](research/washing/008-bingler-2024-climate-cheap-talk.md))

**On the "AI for climate" narrative:**
- AI climate research focuses 4:1 on adaptation over mitigation ([Frontiers 2025](research/narrative/018-ai-climate-resilience-systematic-review-2025.md))
- Most "AI for environment" applications remain studies, not deployments ([Water 2025](research/narrative/020-ai-wastewater-treatment-limits-2025.md))
- Green AI initiatives lack empirical validation - benefits claimed but not verified ([Alzoubi 2024](research/narrative/010-alzoubi-2024-green-ai-initiatives-validation-gap.md))

## Critical Stance

This research applies scrutiny to all claims:
- **Who funded the study?** Industry-funded research is flagged
- **What's the methodology?** Especially for emissions estimates
- **What's missing?** Corporate reports often omit inconvenient data
- **Self-reported vs independent?** Google's water numbers vs Li et al.

---

## How It Works

This repository uses AI-assisted research to systematically collect, analyze, and organize academic literature on AI's environmental impact.

### Search Tools

We query multiple academic databases using their APIs:

- **[OpenAlex](https://openalex.org/)** - Primary source. Open catalog of 240M+ academic papers, citations, and metadata. Free API, no key required.
- **[arXiv](https://arxiv.org/)** - Preprints in CS, physics, and related fields. Captures cutting-edge research before peer review.
- **[Serper](https://serper.dev/)** - Google Search API for news, reports, and Google Scholar results not in academic databases.
- **[Internet Archive](https://archive.org/)** - Wayback Machine for archived versions of corporate sustainability reports and deleted pages.

### Research Process

1. **Search** - Query databases with targeted terms (e.g., "LLM carbon footprint 2025")
2. **Filter** - Focus on 2024-2026 publications, prioritize peer-reviewed and highly-cited work
3. **Extract** - Write an insight (not just the abstract) explaining relevance to our research questions
4. **Store** - Save as individual markdown file with full citation and source URL
5. **Index** - Update topic index for easy navigation

### Repository Structure

```
/research/
  /ghg/                    # Greenhouse gas emissions
    _index.md              # Quick-reference table of all excerpts
    001-author-year-topic.md
    002-author-year-topic.md
    ...
  /water/                  # Water consumption
  /washing/                # Greenwashing analysis
  /datacenters/            # Infrastructure
  /policy/                 # Regulation
  /frugal/                 # Efficient AI
  /community/              # Local impacts
  /narrative/              # "AI for climate" scrutiny

/skills/                   # API query templates (curl commands)
  openalex.md
  arxiv.md
  serper.md
  archive.md
```

Each excerpt is a single insight from a single source, always with a URL. The `_index.md` in each folder provides a scannable summary of all findings.

### Why This Approach

- **Traceable**: Every claim links to a source
- **Updatable**: New research can be added incrementally
- **Searchable**: Markdown files are grep-friendly
- **Transparent**: Methodology and sources are visible

See [RESEARCH_PLAN.md](RESEARCH_PLAN.md) for the full research framework, search terms, and task definitions.
