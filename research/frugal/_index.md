# Frugal AI Index

## Algorithmic Efficiency
| # | Source | Insight | Link |
|---|--------|---------|------|
| 001 | Barbierato & Gatti, 2024 | "Red AI" vs "Green AI" framework - fundamental tension between performance and sustainability | [file](001-barbierato-2024-green-ai-survey.md) |
| 002 | Capogrosso et al., 2024 | TinyML enables ML on milliwatt-scale edge devices, eliminating cloud inference energy costs | [file](002-capogrosso-2024-tinyml-survey.md) |

## Hardware Efficiency
| # | Source | Insight | Link |
|---|--------|---------|------|
| 003 | Zeng et al., 2024 | FlightLLM FPGA achieves **6x energy efficiency** over NVIDIA V100S GPU | [file](003-zeng-2024-flightllm-fpga.md) |
| 004 | Duan et al., 2024 | Memristor neuromorphic chips: paradigm shift from von Neumann for brain-inspired efficiency | [file](004-duan-2024-memristor-neuromorphic.md) |
| 006 | Weilenmann et al., 2024 | Single memristor can emulate multiple synaptic functions for hardware efficiency | [file](006-weilenmann-2024-memristor-synaptic.md) |
| 012 | Stojkovic et al., 2025 | DynamoLLM: Energy-efficient LLM inference clusters through dynamic scaling and workload-aware allocation | [file](012-stojkovic-2025-dynamollm-energy-efficient-inference.md) |
| 013 | Hua, Shen et al., 2025 | Photonic accelerator with 16,000+ components: 1 GHz, 3 ns latency for AI matrix operations | [file](013-hua-2025-photonic-accelerator-ultralow-latency.md) |
| 014 | Pazos, Lanza et al., 2025 | Standard silicon transistor exhibits neural/synaptic behaviors - 2-transistor cell vs 24+ in current designs | [file](014-pazos-2025-silicon-transistor-neuromorphic.md) |
| 015 | Lee et al., 2025 | Reconfigurable memristors for low-power neuromorphic systems: addresses von Neumann bottleneck | [file](015-lee-2025-memristor-low-power-neuromorphic.md) |
| 016 | Kachris, 2025 | Survey of hardware accelerators for LLMs: GPUs, FPGAs, custom architectures with energy focus | [file](016-kachris-2025-hardware-accelerators-llm-survey.md) |

## Systemic Context
| # | Source | Insight | Link |
|---|--------|---------|------|
| 005 | Wang et al., 2024 | AI can reduce ecological footprints but industrial sector and trade openness moderate benefits | [file](005-wang-2024-ai-ecological-transitions.md) |

## When NOT to Use AI
| # | Source | Insight | Link |
|---|--------|---------|------|
| 007 | Markelius et al., 2024 | AI hype is "historically unmatched" - overuse driven by FOMO, fake experts, anthropomorphism | [file](007-markelius-2024-ai-hype-planetary-costs.md) |
| 008 | Humphreys et al., 2024 | AI hype creates cybersecurity risks - over-reliance and over-trust lead to poor decisions | [file](008-humphreys-2024-ai-hype-cyber-risk.md) |
| 009 | Zhai et al., 2024 | Over-reliance on AI degrades cognitive abilities - 578 citations, systematic review | [file](009-zhai-2024-ai-overreliance-cognitive.md) |
| 010 | Hollmann et al., 2025 | Gradient-boosted trees dominated tabular data for 20 years; deep learning hasn't changed this | [file](010-hollmann-2025-tabpfn-tabular-data.md) |
| 011 | Collins et al., 2024 | TRIPOD+AI guideline treats regression and ML as equivalent - choice should be task-based | [file](011-collins-2024-tripod-ai-reporting.md) |

**Key Approaches**: Algorithmic (TinyML, quantization), Hardware (FPGA, memristors, neuromorphic, photonics), Systemic (deployment decisions), When NOT to Use AI (hype critique, appropriate model selection)

## 2025 Updates (January 2025)

New hardware efficiency research in 2025 shows three promising directions:
1. **LLM Inference Optimization** - DynamoLLM demonstrates production-scale energy savings through intelligent cluster design
2. **Photonic Computing** - Large-scale integration (16,000+ components) now achievable with competitive performance
3. **Neuromorphic Advances** - Standard CMOS can achieve neuromorphic functions (2-transistor vs 24+); memristor research maturing

---

## 2026 Refresh — Measured Efficiency in Deployed Systems (September 2026)

Added 2026-09-19. Focus: energy measured in joules on real hardware, deployed serving stacks, and
reasoning / test-time compute — none of which the 2024-2025 entries above cover.

### Reasoning and Test-Time Compute
| # | Source | Insight | Link |
|---|--------|---------|------|
| 017 | Oviedo et al. (Microsoft), 2026, *Joule* | Production serving modelled at **0.31 Wh/query** median (IQR 0.16-0.60) on 8xH100 FP8; test-time scaling raises it **13x to 3.91 Wh**; claims public estimates overstate by 4-20x | [file](017-oviedo-2026-production-inference-energy-test-time-scaling.md) |
| 018 | Morrison, Smith & Strubell, 2026 | Olmo 3 32B: reasoning post-training used **17x** the datacenter energy of the instruction variant (98,464 vs 5,659 kWh), 87% from RL rollouts; development = **82.2%** of total compute | [file](018-morrison-2026-olmo3-reasoning-posttraining-17x.md) |
| 019 | Manya, Hsu & Vandenbergh et al., 2026 | Reasoning modes estimated at **15-20x** non-reasoning energy across 10 commercial models; prompt changes save a further 4-63% | [file](019-manya-2026-reasoning-vs-nonreasoning-consumer-energy.md) |
| 020 | Zhai et al., 2026 | **61-93%** of reasoning steps truncatable without changing the answer; proves over-thinking is structural under length-agnostic rewards, not a per-model bug | [file](020-zhai-2026-reasoning-redundancy-structural.md) |

### Serving Stack — Measured, Not Modelled
| # | Source | Insight | Link |
|---|--------|---------|------|
| 021 | Delavande, Pierrard & Luccioni (Hugging Face), 2026 | On H100: INT8 used **2-3x MORE** energy than FP32 in memory-bound decode; precision only helps in compute-bound prefill (up to 4x); arrival shaping cut per-request energy **100x** | [file](021-delavande-2026-quantization-batching-serving-energy.md) |
| 022 | Dutta et al. (IIT-KGP / Accenture), 2026 | Speculative decoding ranged from **2.51x saving to 1.6x penalty**; summarisation workloads reverse the sign | [file](022-dutta-2026-speculative-decoding-energy.md) |
| 023 | Alfarizy et al., 2026 | MoE sparsity did not transfer to energy: 1.3B-active MoE used **2.1x energy/token** of a dense 1B on Jetson; routing was <9% of the cost, memory footprint was | [file](023-alfarizy-2026-moe-sparsity-edge-energy.md) |

### Hardware and Benchmarks
| # | Source | Insight | Link |
|---|--------|---------|------|
| 024 | Golden, Wu, Wei & Brooks (Harvard / Meta), 2026 | Seven accelerator families measured: no winner across the design space; idle power **20% of TDP (NVIDIA/AMD) vs 80% (Cerebras)**; Cerebras reaches H100 energy parity only above 34% duty cycle | [file](024-golden-2026-accelerator-competition-idle-power.md) |
| 025 | Chung, Wu, Ma & Chowdhury (Michigan / ML.ENERGY), 2026 | 46 models, 1,858 configs, H100+B200: task type alone swings energy **25x**, utilisation another **3-5x** — published per-query figures are not comparable across sources | [file](025-chung-2026-inference-energy-diagnosis-variance.md) |

### The Limits of Efficiency
| # | Source | Insight | Link |
|---|--------|---------|------|
| 026 | Wright, Igel, Samuel & Selvan, 2023/2025 CACM | **Corrected excerpt — supersedes /research/ghg/018 and /research/water/023.** Full text read: the argument is that compute efficiency ≠ energy ≠ carbon efficiency, not that scale overwhelms efficiency. Four authors, not three. Rebound is argued, not measured | [file](026-wright-2025-efficiency-not-enough-corrected.md) |

**Pattern across 021-023:** every efficiency technique validated on a proxy metric — FLOPs, latency,
precision width — was energy-neutral or energy-negative in at least one measured regime. Joules are not a
monotone function of any of them.
