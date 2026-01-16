# BERT Fine-Tuning: Energy and Carbon Across Tasks, Hardware, Methods

**Topic:** GHG Emissions - Numbers Compilation
**Source:** Wang, Na, Strubell, Friedler & Luccioni, 2023
**URL:** https://doi.org/10.18653/v1/2023.findings-emnlp.607

## Key Insight

While existing work on AI energy/carbon focuses on pre-training, fine-tuning is performed "more frequently by many more individual actors" and must be accounted for in NLP's energy footprint.

## Methodology

| Dimension | Variables Tested |
|-----------|------------------|
| Tasks | Multiple NLP benchmark tasks |
| Datasets | Various sizes and domains |
| Hardware | Different GPU/accelerator configurations |
| Measurement modalities | Multiple approaches to energy measurement |

## Key Findings

- Single pre-training run draws "substantially more energy" than fine-tuning
- BUT fine-tuning happens much more often, by many more people
- Aggregate fine-tuning energy may rival or exceed pre-training
- Energy costs vary significantly across:
  - Different NLP tasks
  - Different dataset sizes
  - Different hardware infrastructure
  - Different measurement approaches
- Results allow placing fine-tuning "into perspective" relative to pre-training and inference

## Recommendations from Authors

- Researchers and practitioners should consider fine-tuning energy in total footprint
- Hardware choice significantly impacts energy consumption
- Measurement methodology matters for accurate assessment
- Provides recommendations for improving fine-tuning energy efficiency

## Why This Matters

- Published at EMNLP 2023 (top NLP venue) - peer-reviewed methodology
- Authors include Strubell and Luccioni - leading researchers on AI energy
- First systematic study of fine-tuning energy across multiple dimensions
- Shifts attention from just pre-training to full lifecycle
- Actionable: gives practitioners data to make informed decisions
- 10 citations (2023 paper) - emerging influential work

## Implications for GHG Accounting

- Pre-training emissions often attributed to model developers (OpenAI, Meta, etc.)
- Fine-tuning emissions distributed across thousands of organizations/individuals
- Current GHG accounting may undercount total emissions by ignoring fine-tuning
- Need for standardized methodology to track fine-tuning emissions

---
Retrieved: 2026-01-16
Search: OpenAlex
