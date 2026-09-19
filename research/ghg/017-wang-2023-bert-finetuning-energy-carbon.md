# One BERT pre-training run costs 368 kWh, equal to between 392 and 45,109 fine-tuning runs depending on the task

**Topic:** GHG emissions — where energy sits across the pre-train, fine-tune and inference phases
**Source:** Xiaorong Wang, Clara Na, Emma Strubell, Sorelle A. Friedler, Sasha Luccioni
**Type:** peer-reviewed (Findings of EMNLP 2023)
**URL:** https://aclanthology.org/2023.findings-emnlp.607/
**Source note:** DOI https://doi.org/10.18653/v1/2023.findings-emnlp.607
**Published:** 2023-12

## Finding

Pre-training BERT-base from scratch on four RTX 8000 GPUs consumed 368.0 kWh over 357 hours and emitted 174.6 kg CO2. Fine-tuning the same model costs between 0.008 kWh (RTE, 6K examples) and 0.938 kWh (MNLI, 433K examples), so a single pre-training run equals 392 MNLI-scale fine-tunings or 45,109 RTE-scale ones. Energy scales with the number of tokens seen, including padding tokens, more predictably than with optimisation steps or example counts. Sequence length drives fine-tuning energy far more than it drives inference energy: fine-tuning per 1,000 examples ranges from 0.40e-3 to 3.04e-3 kWh across tasks, while inference over the same tasks ranges only from 0.65e-3 to 1.24e-3 kWh.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| BERT-base pre-training, 4 GPUs | 368.0 kWh, 174.6 kg CO2, 357 hr | measured, CodeCarbon x 1.059 wall-meter correction; 900k steps at seq len 128 plus 100k at 512 |
| BERT-base pre-training, 1 GPU (extrapolated) | 419.6 kWh, 199.1 kg CO2, 673 hr | extrapolated from a 12-hour partial run |
| Fine-tune RTE (NLI, 6K ex.) | 0.008 kWh, 0.004 kg CO2, 59 s | measured, 1 GPU |
| Fine-tune MNLI (NLI, 433K ex.) | 0.938 kWh, 0.445 kg CO2, 6,700 s | measured, 1 GPU |
| Fine-tune SQuAD v1 (98K ex.) | 0.537 kWh, 0.255 kg CO2 | measured, 1 GPU |
| Fine-tune SQuAD v2 (142K ex.) | 0.795 kWh, 0.377 kg CO2 | measured, 1 GPU |
| Fine-tune IMDB (50K ex.) | 0.151 kWh | measured, 1 GPU |
| Fine-tune SST2 (70K ex.) | 0.081 kWh | measured, 1 GPU |
| Fine-tune CoNLL2003 (21K ex.) | 0.021 kWh | measured, 1 GPU |
| Fine-tune CoNLL2012 (143K ex.) | 0.207 kWh | measured, 1 GPU |
| Pre-training expressed in fine-tuning runs | 392 (MNLI) to 45,109 (RTE) | ratio of the measured values above |
| DistilBERT distillation | 187.74 kWh, 89.08 kg CO2, 175.5 hr | measured; a further ~50% on top of pre-training cost |
| Distillation amortisation | 86 (MNLI-like) to 47,000 (RTE-like) fine-tuning runs | calculated; DistilBERT fine-tuning uses ~50% less energy |
| Fine-tuning energy per 1,000 examples | 0.40e-3 to 3.04e-3 kWh | measured across 8 tasks |
| Inference energy per 1,000 examples | 0.65e-3 to 1.24e-3 kWh | measured, batch size 1, 1 GPU |
| Grid factor, Pittsburgh PA | 1,046.1 lb CO2/MWh | EPA Power Profiler |
| Grid factor, Haverford PA | 672.8 lb CO2/MWh | EPA Power Profiler |

## Methodology

BERT-base was pre-trained from scratch on BookCorpus plus the 2020 Wikipedia dump, masked-language-modeling objective only, on the same machines later used for fine-tuning so that the two phases are directly comparable. Two hardware platforms were used, one 4 x A100 machine and one 4 x RTX 8000 machine; pre-training used all four GPUs, fine-tuning used one. Energy came from CodeCarbon, calibrated against a physical wall meter, yielding a fixed power-loss coefficient of 1.059 applied to every reading. Carbon conversion used EPA Power Profiler grid factors for the two server locations. Sequences were dynamically padded to the batch maximum, and the authors report the resulting effective token count as the predictor of energy. Inference figures use single-example batches.

## Limitations and conflicts

Funding is disclosed as an NSF Graduate Research Fellowship (DGE2140739); affiliations are Haverford College, Carnegie Mellon University, the Allen Institute for AI and Hugging Face, with no industry sponsorship of the measurements. The authors state their own scope limit: experiments cover only token classification, sequence classification and question answering with BERT-base and DistilBERT-base, and they explicitly decline to extrapolate to larger language models, other architectures, or tasks such as summarization. Batch-size-1 inference is a lower bound on efficiency and the authors say deployed inference is typically optimised well beyond it. The 1-GPU pre-training figure is extrapolated from a 12-hour partial run, not measured to completion. Two grid factors are used for two different server rooms, so carbon figures across tables are not on one basis. The paper measures operational energy only; no embodied hardware emissions.

Note on what the paper does and does not claim about aggregate fine-tuning. The paper establishes that a single pre-training run draws substantially more energy than a single fine-tuning run and quantifies that ratio. Its argument for counting fine-tuning is that it is performed more frequently by many more individual actors. The paper supplies no estimate of how many fine-tuning runs occur in practice and therefore makes no measured or modelled claim that aggregate fine-tuning rivals aggregate pre-training. The ratios above are the boundary on any such claim: it would require more than 392 MNLI-scale fine-tunings per pre-training run to hold for that task.

## Relation to existing corpus

Shares instrument (CodeCarbon) and two authors with the inference measurements in community/001, and covers the training-side phase that study leaves out. The 368 kWh pre-training figure is for a 110M-parameter 2018 model and is three orders of magnitude below the BLOOM-scale training energy cited in community/001 (51,686 kWh for a 7B model), which bounds how far BERT-era figures can be carried forward.

---
Retrieved: 2026-09-19
Search: ACL Anthology PDF for 2023.findings-emnlp.607, text-extracted locally
