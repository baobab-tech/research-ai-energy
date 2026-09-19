# Image generation draws 2.907 kWh per 1,000 inferences against 0.002 kWh for text classification, a spread of more than 1,450x across ML tasks

**Topic:** Model energy — measured inference cost by task, modality and architecture
**Source:** Alexandra Sasha Luccioni, Yacine Jernite, Emma Strubell
**Type:** peer-reviewed (ACM FAccT '24)
**URL:** https://doi.org/10.1145/3630106.3658542
**Source note:** open version https://arxiv.org/abs/2311.16863 (v3, 15 October 2024)
**Published:** 2024-06

## Finding

Luccioni, Jernite and Strubell measured energy and carbon for 1,000 inferences on each of 88 models across 10 tasks and 30 datasets, on a fixed hardware and grid configuration. Task structure accounts for more of the variation than parameter count does: the mean for image generation is 2.907 kWh per 1,000 inferences against 0.002 kWh for text classification, a factor above 1,450. Holding the task fixed, multi-purpose zero-shot models cost roughly an order of magnitude more than task-specific fine-tuned models on discriminative tasks, with extractive question answering on SciQ at 0.3 g CO2eq per 1,000 inferences for the most efficient task-specific model against 10 g for multi-purpose models. The gap narrows on summarization, where task-specific sequence-to-sequence models emit 4 to 10 g against 20 to 30 g for multi-purpose models, and the authors attribute that residual gap mostly to model size.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Text classification | 0.002 kWh (sd 0.001) / 1,000 inferences | measured, CodeCarbon, GPU+CPU+RAM of one node; batch size 1 |
| Extractive QA | 0.003 kWh (sd 0.001) | same |
| Masked language modeling | 0.003 kWh (sd 0.001) | same |
| Token classification | 0.004 kWh (sd 0.002) | same |
| Image classification | 0.007 kWh (sd 0.001) | same |
| Object detection | 0.038 kWh (sd 0.02) | same |
| Text generation | 0.047 kWh (sd 0.03) | same; 10 new tokens generated per input |
| Summarization | 0.049 kWh (sd 0.01) | same |
| Image captioning | 0.063 kWh (sd 0.02) | same |
| Image generation | 2.907 kWh (sd 3.31) | same; median 1.35 kWh, distribution heavily skewed |
| Ratio, most to least intensive task | >1,450x | measured, across the 88 models |
| stable-diffusion-xl-base-1.0 | 1,594 g CO2eq / 1,000 inferences | measured at 297.6 g CO2eq/kWh; equals 4.1 miles of average US petrol car |
| distilbert-base-uncased | 0.0006 miles equivalent, 6,833x less | same grid factor |
| Least efficient image generation model | 11.49 kWh / 1,000 inferences | equals 522 smartphone charges at 0.022 kWh each, about half a charge per image |
| Flan-T5-base (222M) zero-shot | 0.026 kWh / 3.67 g CO2eq | mean over text classification, QA, summarization |
| Flan-T5-xxl (11B) zero-shot | 0.083 kWh / 11.48 g CO2eq | same |
| BLOOMz-560M zero-shot | 0.054 kWh / 7.5 g CO2eq | same |
| BLOOMz-7B zero-shot | 0.104 kWh / 14.46 g CO2eq | same |
| BLOOMz-7B training + fine-tuning | 51,686 + 7,571 kWh | training from Luccioni et al. BLOOM logs; fine-tuning estimated from BLOOMz training logs via GPU TDP |
| BLOOMz-7B inference/training parity | 592,570,000 inferences | calculated from the two rows above |
| BLOOMz-560M inference/training parity | 204,592,592 inferences | same method |
| Energy for the study itself | 754.66 kWh / 178.97 kg CO2eq | all experimentation and evaluation |

## Methodology

Direct measurement on one node of 8 NVIDIA A100-SXM4-80GB GPUs hosted on AWS in us-west-2 (Oregon), at a stated average grid carbon intensity of 297.6 g CO2eq per kWh. Energy was recorded with CodeCarbon, which reports a GPU, CPU and RAM breakdown. Each model ran 1,000 inferences on each of 3 datasets for its task, repeated 10 times. Inferences were run sequentially with no batching, chosen to reflect deployment where inputs cannot be batched. Experiments used a single GPU, but idle draw from the other seven GPUs on the node is included in the reported figures. Task-specific models were the 8 most-downloaded Hugging Face models per task; multi-purpose models were 4 Flan-T5 and 4 BLOOMz sizes prompted zero-shot with a prompt template held constant across models. Accuracy was checked with the `evaluate` library for task-specific models and the LM Evaluation Harness for zero-shot models.

## Limitations and conflicts

Two of the three authors were at Hugging Face, which publishes many of the models measured and hosts the download counts used to select them; the third was at Carnegie Mellon University and the Allen Institute for AI. The paper carries no funding statement and the acknowledgements name only individual reviewers, so no external sponsor is disclosed. Batch size 1 is a lower bound on efficiency: production serving batches requests, so per-inference energy in deployment is lower than these numbers, and the authors say as much about optimised deployment elsewhere. Including idle draw from seven unused GPUs inflates the absolute figures for small models more than for large ones, which widens the measured spread between light and heavy tasks. The image-generation mean of 2.907 kWh carries a standard deviation of 3.31 and a median of 1.35 kWh, so that headline number is driven by a few large models and by output resolution. Only operational energy is measured; embodied emissions of the hardware are excluded, and the paper notes an external estimate that embodied carbon can reach 50% of an LLM's footprint. The models are 2023-era open models topping out at 11B parameters, with no frontier or reasoning model and no retrieval or agentic workload. Carbon figures are specific to one grid region and do not transfer; energy figures do not transfer off A100 hardware. The parity calculation rests on BLOOM training logs and a TDP-based fine-tuning estimate assuming 100% GPU utilisation, so it is an estimate, not a measurement.

## Relation to existing corpus

Provides the per-task measured baseline that later per-query figures are compared against. The task-specific versus generative gap is the measured counterpart to the fine-tuning and pre-training accounting in ghg/017, which shares two authors (Strubell, Luccioni) and the same CodeCarbon instrument.

---
Retrieved: 2026-09-19
Search: arXiv 2311.16863 PDF, text-extracted locally; DOI cross-checked at ACM
