# Frugal AI Index

18 excerpts, every one verified against its source. Summary in [README.md](README.md).

| # | Source | Finding |
|---|--------|---------|
| 001 | [Barbierato & Gatti, 2024](001-barbierato-2024-green-ai-survey.md) | Survey of 48 Green AI papers, clustered by k-means, concluding that accuracy may have to fall |
| 003 | [Zeng et al., 2024](003-zeng-2024-flightllm-fpga.md) | FlightLLM on an Alveo U280 FPGA reaches 6.0x the tokens per joule of a 2019 NVIDIA V100S at batch size 1, and the margin shrinks as batch size rises |
| 006 | [Weilenmann et al., 2024](006-weilenmann-2024-memristor-synaptic.md) | A memristive synapse layer is estimated at 36 mJ per Atari Pong game against 3,464 mJ for a well-utilised A100, a 96x gain that becomes 966x only against an under-utilised GPU |
| 012 | [Stojkovic et al., 2025](012-stojkovic-2025-dynamollm-energy-efficient-inference.md) | Reconfiguring an H100 serving cluster cut measured LLM inference energy 42% over a fixed-configuration baseline, with headline savings of 53% reported from simulation |
| 013 | [Hua et al., 2025](013-hua-2025-photonic-accelerator-ultralow-latency.md) | A 16,000-component photonic accelerator measures 2.38 TOPS/W including lasers, which is no better than a contemporary GPU; its demonstrated advantage is latency, not energy |
| 014 | [Pazos et al., 2025](014-pazos-2025-silicon-transistor-neuromorphic.md) | Two standard 180 nm transistors reproduce neuron and synapse behaviour where CMOS circuits need 24, at a firing energy of 415 pJ per micrometre and with no neural network built |
| 016 | [Kachris, 2025](016-kachris-2025-hardware-accelerators-llm-survey.md) | A survey of 27 transformer accelerators finds energy-efficiency claims spanning 3.1x to 10,000x, each against a different baseline, and none of the ASIC results measured on fabricated silicon |
| 017 | [Oviedo et al., 2026](017-oviedo-2026-production-inference-energy-test-time-scaling.md) | Production-scale LLM inference modelled at 0.31 Wh median per query, rising 13x under test-time scaling |
| 018 | [Morrison et al., 2026](018-morrison-2026-olmo3-reasoning-posttraining-17x.md) | Post-training a reasoning model cost 17x the datacenter energy of its instruction-tuned twin; 82% of total compute was never-released development |
| 019 | [Manya et al., 2026](019-manya-2026-reasoning-vs-nonreasoning-consumer-energy.md) | Reasoning modes estimated at 15–20x the per-query energy of non-reasoning modes for tasks where the non-reasoning answer was judged sufficient |
| 020 | [Zhai et al., 2026](020-zhai-2026-reasoning-redundancy-structural.md) | 61–93% of reasoning steps in frontier chain-of-thought traces can be truncated without changing the answer, and the paper proves this is structural |
| 021 | [Delavande et al., 2026](021-delavande-2026-quantization-batching-serving-energy.md) | INT8 quantisation raised decode energy 2–3x over FP32 on an H100; request arrival shaping cut per-request energy up to 100x |
| 022 | [Dutta et al., 2026](022-dutta-2026-speculative-decoding-energy.md) | Speculative decoding saved 2.51x energy in the best case and cost 1.6x more in the worst; the sign depends on the dataset |
| 023 | [Alfarizy et al., 2026](023-alfarizy-2026-moe-sparsity-edge-energy.md) | MoE sparsity did not deliver its FLOP advantage in energy: an MoE with 1.3B active parameters used 2.1x the energy per token of a dense 1B model on edge hardware |
| 024 | [Golden et al., 2026](024-golden-2026-accelerator-competition-idle-power.md) | Measured across seven accelerator families, no platform wins on energy across all workloads, and specialised silicon idles at 30–80% of TDP |
| 025 | [Chung et al., 2026](025-chung-2026-inference-energy-diagnosis-variance.md) | Across 46 models and 1,858 configurations on H100 and B200, task type alone changes inference energy 25x and GPU utilisation another 3–5x |
| 026 | [Wright et al., 2025](026-wright-2025-compute-energy-carbon-efficiency.md) | Compute efficiency does not imply energy efficiency, and neither implies carbon efficiency |
| 027 | [Luccioni et al., 2024](027-luccioni-2024-power-hungry-processing.md) | Image generation draws 2.907 kWh per 1,000 inferences against 0.002 kWh for text classification, a spread of more than 1,450x across ML tasks |
