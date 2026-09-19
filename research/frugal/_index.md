# Frugal AI Index

## Algorithmic Efficiency
| # | Source | Insight |
|---|--------|---------|
| 001 | [Barbierato & Gatti, 2024](001-barbierato-2024-green-ai-survey.md) | "Red AI" vs "Green AI" framework - fundamental tension between performance and sustainability |
| 002 | [Capogrosso et al., 2024](002-capogrosso-2024-tinyml-survey.md) | TinyML enables ML on milliwatt-scale edge devices, eliminating cloud inference energy costs |

## Hardware Efficiency
| # | Source | Insight |
|---|--------|---------|
| 003 | [Zeng et al., 2024](003-zeng-2024-flightllm-fpga.md) | FlightLLM FPGA achieves **6x energy efficiency** over NVIDIA V100S GPU |
| 004 | [Duan et al., 2024](004-duan-2024-memristor-neuromorphic.md) | Memristor neuromorphic chips: paradigm shift from von Neumann for brain-inspired efficiency |
| 006 | [Weilenmann et al., 2024](006-weilenmann-2024-memristor-synaptic.md) | Single memristor can emulate multiple synaptic functions for hardware efficiency |
| 012 | [Stojkovic et al., 2025](012-stojkovic-2025-dynamollm-energy-efficient-inference.md) | DynamoLLM: Energy-efficient LLM inference clusters through dynamic scaling and workload-aware allocation |
| 013 | [Hua, Shen et al., 2025](013-hua-2025-photonic-accelerator-ultralow-latency.md) | Photonic accelerator with 16,000+ components: 1 GHz, 3 ns latency for AI matrix operations |
| 014 | [Pazos, Lanza et al., 2025](014-pazos-2025-silicon-transistor-neuromorphic.md) | Standard silicon transistor exhibits neural/synaptic behaviors - 2-transistor cell vs 24+ in current designs |
| 015 | [Lee et al., 2025](015-lee-2025-memristor-low-power-neuromorphic.md) | Reconfigurable memristors for low-power neuromorphic systems: addresses von Neumann bottleneck |
| 016 | [Kachris, 2025](016-kachris-2025-hardware-accelerators-llm-survey.md) | Survey of hardware accelerators for LLMs: GPUs, FPGAs, custom architectures with energy focus |

## Systemic Context
| # | Source | Insight |
|---|--------|---------|
| 005 | [Wang et al., 2024](005-wang-2024-ai-ecological-transitions.md) | AI can reduce ecological footprints but industrial sector and trade openness moderate benefits |

## When NOT to Use AI
| # | Source | Insight |
|---|--------|---------|
| 007 | [Markelius et al., 2024](007-markelius-2024-ai-hype-planetary-costs.md) | AI hype is "historically unmatched" - overuse driven by FOMO, fake experts, anthropomorphism |
| 008 | [Humphreys et al., 2024](008-humphreys-2024-ai-hype-cyber-risk.md) | AI hype creates cybersecurity risks - over-reliance and over-trust lead to poor decisions |
| 009 | [Zhai et al., 2024](009-zhai-2024-ai-overreliance-cognitive.md) | Over-reliance on AI degrades cognitive abilities - 578 citations, systematic review |
| 010 | [Hollmann et al., 2025](010-hollmann-2025-tabpfn-tabular-data.md) | Gradient-boosted trees dominated tabular data for 20 years; deep learning hasn't changed this |
| 011 | [Collins et al., 2024](011-collins-2024-tripod-ai-reporting.md) | TRIPOD+AI guideline treats regression and ML as equivalent - choice should be task-based |

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
| # | Source | Insight |
|---|--------|---------|
| 017 | [Oviedo et al. (Microsoft), 2026, *Joule*](017-oviedo-2026-production-inference-energy-test-time-scaling.md) | Production serving modelled at **0.31 Wh/query** median (IQR 0.16-0.60) on 8xH100 FP8; test-time scaling raises it **13x to 3.91 Wh**; claims public estimates overstate by 4-20x |
| 018 | [Morrison, Smith & Strubell, 2026](018-morrison-2026-olmo3-reasoning-posttraining-17x.md) | Olmo 3 32B: reasoning post-training used **17x** the datacenter energy of the instruction variant (98,464 vs 5,659 kWh), 87% from RL rollouts; development = **82.2%** of total compute |
| 019 | [Manya, Hsu & Vandenbergh et al., 2026](019-manya-2026-reasoning-vs-nonreasoning-consumer-energy.md) | Reasoning modes estimated at **15-20x** non-reasoning energy across 10 commercial models; prompt changes save a further 4-63% |
| 020 | [Zhai et al., 2026](020-zhai-2026-reasoning-redundancy-structural.md) | **61-93%** of reasoning steps truncatable without changing the answer; proves over-thinking is structural under length-agnostic rewards, not a per-model bug |

### Serving Stack — Measured, Not Modelled
| # | Source | Insight |
|---|--------|---------|
| 021 | [Delavande, Pierrard & Luccioni (Hugging Face), 2026](021-delavande-2026-quantization-batching-serving-energy.md) | On H100: INT8 used **2-3x MORE** energy than FP32 in memory-bound decode; precision only helps in compute-bound prefill (up to 4x); arrival shaping cut per-request energy **100x** |
| 022 | [Dutta et al. (IIT-KGP / Accenture), 2026](022-dutta-2026-speculative-decoding-energy.md) | Speculative decoding ranged from **2.51x saving to 1.6x penalty**; summarisation workloads reverse the sign |
| 023 | [Alfarizy et al., 2026](023-alfarizy-2026-moe-sparsity-edge-energy.md) | MoE sparsity did not transfer to energy: 1.3B-active MoE used **2.1x energy/token** of a dense 1B on Jetson; routing was <9% of the cost, memory footprint was |

### Hardware and Benchmarks
| # | Source | Insight |
|---|--------|---------|
| 024 | [Golden, Wu, Wei & Brooks (Harvard / Meta), 2026](024-golden-2026-accelerator-competition-idle-power.md) | Seven accelerator families measured: no winner across the design space; idle power **20% of TDP (NVIDIA/AMD) vs 80% (Cerebras)**; Cerebras reaches H100 energy parity only above 34% duty cycle |
| 025 | [Chung, Wu, Ma & Chowdhury (Michigan / ML.ENERGY), 2026](025-chung-2026-inference-energy-diagnosis-variance.md) | 46 models, 1,858 configs, H100+B200: task type alone swings energy **25x**, utilisation another **3-5x** — published per-query figures are not comparable across sources |

### The Limits of Efficiency
| # | Source | Insight |
|---|--------|---------|
| 026 | [Wright, Igel, Samuel & Selvan, 2023/2025 CACM](026-wright-2025-efficiency-not-enough-corrected.md) | **Corrected excerpt — supersedes /research/ghg/018 and /research/water/023.** Full text read: the argument is that compute efficiency ≠ energy ≠ carbon efficiency, not that scale overwhelms efficiency. Four authors, not three. Rebound is argued, not measured |

**Pattern across 021-023:** every efficiency technique validated on a proxy metric — FLOPs, latency,
precision width — was energy-neutral or energy-negative in at least one measured regime. Joules are not a
monotone function of any of them.
