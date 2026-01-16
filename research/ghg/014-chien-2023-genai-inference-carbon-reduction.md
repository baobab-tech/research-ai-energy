# Generative AI Inference: CarbonMin Strategy Can Reduce Emissions

**Topic:** GHG Emissions - Numbers Compilation
**Source:** Chien, Lin, Nguyen, Rao, Sharma & Wijayawardana, 2023
**URL:** https://doi.org/10.1145/3604930.3605705

## Key Numbers

| Metric | Value | Context |
|--------|-------|---------|
| Focus systems | ChatGPT, DALL-E 2, Stable Diffusion | Generative AI exemplars |
| Request direction strategies | Local, Balance, CarbonMin | Approaches compared for carbon impact |
| Projection horizon | 2035 | Long-term carbon impact modeling |

## Methodology Notes

- Creates workload model using ChatGPT as exemplar for generative AI inference
- Compares three request direction approaches:
  1. **Local**: Route to nearest data center (lowest latency)
  2. **Balance**: Distribute load across data centers (optimize utilization)
  3. **CarbonMin**: Route to lowest-carbon-intensity data center (minimize emissions)
- Assesses power use and carbon impacts of each approach
- Models both current (2023) and future (2035) grid carbon intensities
- Published at ACM HotCarbon 2023 workshop

## Key Insights

- Generative AI applications are "consuming growing quantities of computing"
- Request routing decisions significantly impact carbon emissions
- Carbon-aware scheduling can reduce inference emissions without hardware changes
- Geographic variation in grid carbon intensity creates optimization opportunities
- Future grid decarbonization will change optimal routing strategies

## Why This Matters

- 106 citations - highly influential for carbon-aware AI infrastructure
- Provides actionable methodology for reducing inference emissions
- Shows that software/routing decisions matter, not just hardware efficiency
- Framework applicable to other AI services beyond ChatGPT
- Highlights temporal and spatial variation in carbon intensity

---
Retrieved: 2026-01-16
Search: OpenAlex
