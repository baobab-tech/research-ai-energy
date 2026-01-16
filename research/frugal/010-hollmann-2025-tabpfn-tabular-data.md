# Accurate Predictions on Small Data with a Tabular Foundation Model

**Topic:** Frugal AI - When NOT to Use AI (When Traditional Methods Win)
**Source:** Hollmann, Muller, Purucker, Krishnakumar, Korfer, Hoo, Schirrmeister, Hutter, 2025
**URL:** https://doi.org/10.1038/s41586-024-08328-6

## Insight

Despite deep learning revolutionizing many domains, gradient-boosted decision trees (XGBoost, LightGBM, etc.) have dominated tabular data prediction for the past 20 years. This Nature paper acknowledges that for spreadsheet-style data common across biomedicine, economics, climate science, and materials science, traditional tree-based methods have consistently outperformed neural networks. The new TabPFN model only beats these baselines on datasets with up to 10,000 samples - confirming that for larger tabular datasets, simpler methods remain superior.

## Key Points

- **20-year dominance of simple methods:** Gradient-boosted decision trees have dominated tabular data for two decades, outperforming deep learning
- **Size threshold:** Even state-of-the-art foundation models only outperform traditional methods on small datasets (up to 10,000 samples)
- **Efficiency comparison:** Traditional methods tuned for 4 hours are beaten by TabPFN in 2.8 seconds - but this only holds for small data
- **Ubiquity of tabular data:** Spreadsheet-organized data is ubiquitous across scientific fields, meaning traditional methods should often be preferred
- **Implicit acknowledgment:** Deep learning has NOT revolutionized tabular data prediction despite its success elsewhere

## Notes

- Published in Nature (top-tier journal) with 307 citations as of January 2025
- Key evidence that neural networks are not universally superior - domain matters
- Tabular data applications: biomedical risk models, drug discovery, materials science, economics
- Important nuance: TabPFN succeeds on small data but doesn't claim superiority on large datasets
- Validates continued use of XGBoost, LightGBM, Random Forests for most tabular prediction tasks

---
Retrieved: 2026-01-16
Search: OpenAlex "tabular data simple models deep learning"
