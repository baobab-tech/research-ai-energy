# Gemini Apps: 0.26 mL Water Per Text Prompt

**Topic:** Water Consumption - Numbers Compilation
**Source:** Elsworth, Huang, Patterson, et al. (2025)
**URL:** https://doi.org/10.48550/arxiv.2508.15734

## Key Numbers

| Metric | Value | Context |
|--------|-------|---------|
| Water per prompt | 0.26 mL | Median Gemini Apps text prompt (Google production) |
| Energy per prompt | 0.24 Wh | Median Gemini Apps text prompt |
| Comparison | 5 drops of water | Per text prompt equivalent |
| Energy reduction | 33x | Software efficiency gains over one year |
| Carbon reduction | 44x | Carbon footprint reduction over one year |

## Methodology Notes

- First paper measuring AI serving environmental metrics in a production environment at scale
- Full-stack infrastructure accounting including: active AI accelerator power, host system energy, idle machine capacity, data center energy overhead
- Instrumentation of Google's Gemini assistant infrastructure
- Authors include David Patterson (Google), Jeff Dean, and other Google senior researchers

## Critical Context

- These are Google's self-reported numbers with obvious conflict of interest
- 0.26 mL is substantially lower than Li et al. 2023 estimates (500ml per 20-50 queries implies ~10-25mL per query)
- The 33x and 44x efficiency improvements attributed to "software efficiency efforts and clean energy procurement"
- Paper notes reducing AI serving environmental impact "continues to warrant important attention"
- Comparison metric: watching 9 seconds of television (0.24 Wh energy)

## Discrepancy with Li et al. 2023

- Li et al. estimated 500mL per 20-50 queries = 10-25mL per query for ChatGPT
- Google claims 0.26mL per Gemini query = ~40-100x lower than Li et al. estimates
- Possible explanations: different models, infrastructure efficiency, methodology differences
- Requires independent verification

---
Retrieved: 2026-01-16
Search: OpenAlex
