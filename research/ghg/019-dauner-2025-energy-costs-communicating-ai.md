# Energy Costs of Communicating with AI

**Topic:** GHG Emissions - Inference Measurement
**Source:** Dauner & Socher, 2025
**URL:** https://doi.org/10.3389/fcomm.2025.1572947

## Insight

This 2025 paper provides one of the first comprehensive empirical measurements of LLM inference energy costs across multiple models. Testing 14 LLMs ranging from 7 to 72 billion parameters on the MMLU benchmark, the authors measured actual CO2 emissions using the Perun framework on an NVIDIA A100 GPU. The key finding: larger models with reasoning capabilities achieve higher accuracy (up to 84.9%) but incur substantially higher emissions, driven largely by increased token output. This quantifies the accuracy-sustainability trade-off that defines the "Red AI vs Green AI" tension.

## Key Data

- **14 LLMs tested**: 7 billion to 72 billion parameters
- **Benchmark**: 500 multiple-choice + 500 free-response MMLU questions across 5 subjects
- **Measurement**: Perun framework on NVIDIA A100 GPU
- **Emission factor**: 480 gCO2/kWh
- **Finding**: Strong correlation between model size, reasoning behavior, token generation, and emissions
- **Accuracy ceiling**: Reasoning-enabled models achieve up to 84.9% accuracy but at substantially higher emission cost
- **Domain variation**: Abstract/symbolic tasks (e.g., Abstract Algebra) demand more computation but yield lower accuracy

## Critical Analysis

This is one of the most rigorous 2025 studies on inference emissions:
- Uses actual hardware measurement (A100), not theoretical estimates
- Tests across model sizes and reasoning capabilities
- Reveals subject-matter variation in efficiency
- Emission factor (480 gCO2/kWh) is conservative (higher than many grids)
- Highlights that "reasoning" models have different energy profiles than standard inference

## Implications

- Task selection matters: some subjects are inherently more compute-intensive per accuracy point
- Model selection involves accuracy-emissions trade-off
- Token output is a major driver of emissions (important for verbose AI responses)
- Future LLM development must consider "more efficient reasoning strategies"

---
Retrieved: 2026-01-16
Search: OpenAlex "Luccioni AI emissions energy" 2025
