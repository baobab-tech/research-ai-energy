# Frugal AI

26 excerpts on efficiency: what reduces energy in deployed systems, what does not, and the limits
of efficiency as a strategy.

[Full index](_index.md)

## Efficiency techniques measured in joules

Techniques validated on proxy metrics such as precision width, latency and FLOPs do not reliably
reduce energy. Measured results:

| Technique | Result | Hardware | Source |
|---|---|---|---|
| INT8 against FP32 | 2 to 3x **more** energy in memory-bound decode | H100 | [021](021-delavande-2026-quantization-batching-serving-energy.md) |
| Speculative decoding | 2.51x saving to 1.6x **penalty** by dataset | varies | [022](022-dutta-2026-speculative-decoding-energy.md) |
| MoE sparsity, 1.3B active | 2.1x energy per token of a dense 1B | Jetson | [023](023-alfarizy-2026-moe-sparsity-edge-energy.md) |

Routing accounted for under 9% of the MoE cost. The sign reversals come from memory-bound
decode, where arithmetic width stops governing energy.

## Reasoning and test-time compute

The largest 2025 and 2026 development for AI energy.

- Reasoning post-training used 17x the datacentre energy of the instruction variant of the same
  base model on the same cluster: 98,464 against 5,659 kWh, 87% of it RL rollout generation
  ([018](018-morrison-2026-olmo3-reasoning-posttraining-17x.md)).
- Development runs were 82.2% of total compute in that work, so a training figure counting only
  the final run understates by about 5x.
- Test-time scaling multiplies per-query energy roughly 13x, from 0.31 to 3.91 Wh median,
  full-node and PUE-inclusive ([017](017-oviedo-2026-production-inference-energy-test-time-scaling.md)).
  An independent client-side method estimates 15 to 20x across ten commercial models
  ([019](019-manya-2026-reasoning-vs-nonreasoning-consumer-energy.md)).
- Between 61 and 93% of reasoning steps are truncatable without changing the answer, making
  over-thinking structural under length-agnostic training
  ([020](020-zhai-2026-reasoning-redundancy-structural.md)).

## Published figures are not comparable

Across 46 models and 1,858 configurations on H100 and B200, task type alone swings energy 25x and
utilisation a further 3 to 5x ([025](025-chung-2026-inference-energy-diagnosis-variance.md)). That
range is wide enough to contain both sides of most published disputes without either party
miscounting. Any per-query figure requires the model, hardware, precision, batch regime and task
type to be interpretable.

Specialised accelerators idle at 30 to 80% of TDP against about 20% for NVIDIA and AMD parts.
Cerebras reaches H100 energy-per-token parity only above a 34% duty cycle
([024](024-golden-2026-accelerator-competition-idle-power.md)). This is the test to apply to any
claim that a part is "Nx more efficient than a GPU", including the claims in
[003](003-zeng-2024-flightllm-fpga.md), [013](013-hua-2025-photonic-accelerator-ultralow-latency.md)
and [016](016-kachris-2025-hardware-accelerators-llm-survey.md).

## Correction held in this folder

[026](026-wright-2025-efficiency-not-enough-corrected.md) is a corrected excerpt of Wright, Igel,
Samuel & Selvan, written from the full text. It supersedes
[ghg/018](../ghg/018-wright-2025-efficiency-not-enough.md) and
[water/023](../water/023-wright-2025-efficiency-not-enough-sustainable-ai.md), which were written
from the abstract, omit an author, and misstate the thesis. The paper's lead argument is that
compute efficiency, energy efficiency and carbon efficiency are distinct and non-substitutable.
Rebound is its third point and is argued, not measured.

## Gaps

- No 2026 empirical work on AI rebound effects. Position papers only.
- FP4 on Blackwell is unmeasured. The INT8 penalty above should not be generalised to
  hardware-native FP4.
- Agentic and multi-turn workloads. Per-query studies exclude tool calling by construction.
- MLPerf Power v6.0 and v6.1 publish no summary figures normalised to joules per token.
- No documented case of a classical method matching an LLM at a fraction of the energy. The
  nearest results report accuracy, not joules.
