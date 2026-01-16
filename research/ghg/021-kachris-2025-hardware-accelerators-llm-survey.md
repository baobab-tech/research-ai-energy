# A Survey on Hardware Accelerators for Large Language Models

**Topic:** GHG Emissions - Hardware Efficiency
**Source:** Kachris, 2025
**URL:** https://doi.org/10.3390/app15020586

## Insight

This 2025 survey from the University of West Attica provides a comprehensive examination of hardware accelerators designed to enhance LLM performance and energy efficiency. The paper covers GPUs, FPGAs, and custom-designed architectures, analyzing their architecture, performance metrics, and energy efficiency considerations. As LLMs scale to hundreds of billions of parameters, specialized hardware becomes critical for sustainable deployment - this survey maps the landscape of solutions addressing the computational demands of LLM inference.

## Key Data

- **Hardware types covered**: GPUs, FPGAs, custom-designed architectures
- **Analysis dimensions**: Architecture, performance, energy efficiency
- **Target audience**: Researchers, engineers, decision-makers optimizing LLM deployment
- **13 citations** in early 2025 indicates strong research interest
- **Focus**: Real-world deployment optimization for LLMs

## Why Hardware Matters for AI Emissions

- LLM inference at scale requires specialized hardware
- Energy efficiency varies significantly across accelerator types
- Custom architectures can achieve order-of-magnitude efficiency gains (cf. FlightLLM FPGA paper)
- Hardware selection directly impacts per-query carbon footprint
- Accelerator choice determines whether efficiency gains translate to reduced emissions

## Hardware Options Compared

| Type | Characteristics | Energy Efficiency |
|------|----------------|-------------------|
| GPUs | General purpose, flexible | Baseline |
| FPGAs | Reconfigurable, lower latency | Higher efficiency potential |
| Custom ASICs | Task-specific, highest throughput | Highest efficiency but inflexible |

## Notes

- Published in Applied Sciences (MDPI) - peer-reviewed
- Single author survey (Kachris) from Athens
- Complements efficiency research with hardware perspective
- Decision-makers choosing deployment hardware need energy efficiency data
- Gap: Survey doesn't quantify absolute energy consumption per accelerator type

---
Retrieved: 2026-01-16
Search: OpenAlex "LLM energy consumption carbon" 2025
