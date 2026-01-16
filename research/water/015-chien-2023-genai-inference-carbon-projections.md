# ChatGPT Carbon Impact: Current and 2035 Projections

**Topic:** Water Consumption - Numbers Compilation
**Source:** Chien, Lin, Nguyen, Rao, Sharma, Wijayawardana (2023)
**URL:** https://doi.org/10.1145/3604930.3605705

## Key Numbers

| Metric | Value | Context |
|--------|-------|---------|
| Focus | Compute, energy, carbon | Generative AI inference workloads |
| Exemplar | ChatGPT | Workload model created |
| Approaches compared | 3 | Local, Balance, CarbonMin request direction |
| Projection timeline | 2035 | Future carbon impact assessment |

## Methodology Notes

- Workshop on Sustainable Computer Systems (ACM HotCarbon 2023)
- Uses ChatGPT as exemplar to create workload model
- Studies power use and carbon impacts of different request routing strategies
- Compares infrastructure placement strategies for carbon minimization

## Request Direction Strategies

| Strategy | Description | Carbon Impact |
|----------|-------------|---------------|
| Local | Serve from nearest data center | Baseline |
| Balance | Load balancing across centers | Variable |
| CarbonMin | Route to lowest-carbon location | Reduced |

## Key Insight: Infrastructure Design Matters

- Request routing strategy significantly affects total carbon footprint
- Carbon-aware scheduling can reduce environmental impact
- Water consumption indirectly affected by energy source (cooling loads vary by location)
- 2035 projections show growing importance of sustainable AI infrastructure

## Relation to Water Consumption

- Energy consumption directly correlates with cooling water needs
- CarbonMin approach may route to cleaner energy but water-intensive regions
- Need holistic approach considering both carbon AND water footprints
- Data center location decisions have long-term environmental implications

---
Retrieved: 2026-01-16
Search: OpenAlex
