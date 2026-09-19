# Measured on one A100: 14 open-weight LLMs span 27.7 to 2,042 gCO2e for the same 1,000 questions, a 74x spread driven by reasoning token output rather than parameter count

**Topic:** GHG emissions — measured inference energy across models
**Source:** Maximilian Dauner and Gudrun Socher — Munich Center for Digital Sciences and AI, HM Hochschule München, 2025
**Type:** peer-reviewed (brief research report)
**URL:** https://doi.org/10.3389/fcomm.2025.1572947
**Published:** 2025-06

## Finding

Fourteen open-weight models from 7B to 72B parameters answered the same 500 MMLU questions twice, once constrained to a multiple-choice index and once free-response, on a single local NVIDIA A100 80GB with device-level energy instrumentation. Across the combined 1,000 questions the total ranges from 27.7 gCO2e (Qwen 7B, 32.9% accuracy) to 2,042.4 gCO2e (DeepSeek-R1 70B, 78.9%). The driver is generated token count, not parameter count: enabling reasoning on the same model multiplies emissions 4-6x, and the most efficient point on the accuracy frontier is Cogito 70B in reasoning mode at 1,341.1 gCO2e for 84.9% accuracy, which beats DeepSeek-R1 70B on both axes. Twelve of the fourteen systems stay under 500 gCO2e, and none of those twelve exceeds 80% accuracy.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Models tested | 14, 7B-72B parameters | Llama 3.1 8B/70B, Llama 3.3 70B, Qwen 7B/72B, Qwen2.5 7B/72B, Cogito 8B/70B (standard and reasoning), DeepSeek-R1 7B/8B/70B |
| Hardware | single NVIDIA A100 80GB, local | measured |
| Instrumentation | Perun framework | device-level counters (NVML for GPU, RAPL for CPU and DRAM); not wall-plug metering |
| Emission factor | 480 gCO2/kWh | Ember Global Electricity Review 2024 global average, applied uniformly |
| Multiple-choice phase, 500 questions | 1.25 g (Cogito 8B default) to 717.31 g (DeepSeek-R1 70B) | measured |
| Free-response phase, 500 questions | 26.28 g (Qwen 7B) to 1,325.12 g (DeepSeek-R1 70B) | measured |
| Combined, 1,000 questions, lowest | 27.7 gCO2e at 32.9% accuracy (Qwen 7B) | measured |
| Combined, 1,000 questions, highest | 2,042.4 gCO2e at 78.9% accuracy (DeepSeek-R1 70B) | measured |
| Best accuracy | 84.9% at 1,341.1 gCO2e (Cogito 70B, reasoning) | 34.3% less CO2e than DeepSeek-R1 70B at 6 points higher accuracy |
| Mid-range reference | 426.8 gCO2e at 77.6% accuracy (Qwen2.5 72B) | under a third of Cogito 70B reasoning |
| Reasoning penalty, same model | 4-6x | Cogito 8B free-response: 371.87 g reasoning vs 56.30 g default; Cogito 70B multiple-choice: 411.72 g vs 8.20 g |
| Scale penalty, same family | ~7x | Qwen2.5 72B 418.12 g vs Qwen2.5 7B 60.63 g, free-response |
| Derived energy per question, lowest | 0.058 Wh | 27.7 g ÷ 480 g/kWh ÷ 1,000; derived, device-level, no PUE |
| Derived energy per question, highest | 4.26 Wh | 2,042.4 g ÷ 480 g/kWh ÷ 1,000; derived |
| Response tokens, multiple-choice | 37.7 per question average | plus 543.5 thinking tokens for reasoning variants |
| Response tokens, free-response | 435.2 per question average | thinking tokens average 859.2 per reasoning run |
| Longest single output | 37,575 tokens (Cogito 8B reasoning, Abstract Algebra) | measured |
| Accuracy by subject, multiple-choice | 76.3% High School World History to 51.4% Abstract Algebra | five subjects, 100 questions each |
| Accuracy by subject, free-response | 69.4% High School Mathematics to 52.1% Philosophy | |

## Methodology

Five MMLU subjects (Philosophy, High School World History, International Law, Abstract Algebra, High School Mathematics), 100 questions each. Phase one constrains standard models to a single-token answer index; reasoning models are left unconstrained because they need intermediate text. Phase two removes the length limit for all models and grades free-text answers with OpenAI o4-mini as judge, given the question, options, correct answer and model output. Energy is captured by Perun, which reads hardware power counters rather than a wall socket, so the figures cover the GPU and host devices only. Nothing outside the machine is included: no PUE, no cooling, no networking, no embodied hardware, no training energy. The emission factor is a single global average applied to every measurement.

## Limitations and conflicts

No funding was received and no commercial or financial relationship is declared. Generative AI was used only for spell-checking. The authors are at a university of applied sciences with no stated industry tie.

The measurement boundary is narrower than most comparable studies. Device counters exclude the roughly 10-60% overhead that PUE, cooling and networking add in a real data centre, and the paper does not state which Perun sensors were enabled, so whether CPU and DRAM draw is inside the reported totals is unclear. A single A100 running one model at a time is not a production serving configuration, where batching and multi-tenancy change energy per query substantially in the opposite direction. All models are open-weight and locally hosted; no frontier commercial model is measured, and the authors say the results do not extrapolate to models of several hundred billion parameters. Using o4-mini as grader introduces an unmeasured and unreported energy cost of its own, and grader error is not quantified. The 480 gCO2/kWh factor is a global average rather than the German grid the experiment actually ran on, so the CO2e values are a linear rescaling of energy, not a carbon measurement. Two internal inconsistencies survive into the published text. The results section gives DeepSeek-R1 7B's maximum reasoning burden as 6,716 tokens while the discussion gives 14,187 tokens for the same model on a mathematics question. The discussion also describes Cogito 70B reasoning as "a relative improvement of 7.6 percentage points over the Deepseek-R1 70B" when the stated accuracies differ by 6.0 points; 7.6 points is the gap to its own non-reasoning counterpart.

## Relation to existing corpus

The derived per-question range of 0.058 to 4.26 Wh brackets the 0.31 Wh median measured in `research/ghg/026-oviedo-2026-per-query-inference-energy.md`, which is full-node and PUE-inclusive and therefore uses a wider boundary; the agreement of a device-level open-model measurement with a full-node frontier-model measurement at the same order of magnitude is the more useful result than either alone. The 3.91 Wh that file reports under test-time scaling matches this study's reasoning-mode figures closely. The finding that token output rather than parameter count sets inference energy qualifies the parameter-count framing in `research/ghg/004-raiaan-2024-llm-challenges.md`.

---
Retrieved: 2026-09-19
Search: DOI 10.3389/fcomm.2025.1572947; Frontiers open-access PDF extracted locally
