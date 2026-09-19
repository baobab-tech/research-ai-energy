# Frugal AI

18 excerpts, every one verified against its source. What reduces energy in deployed systems,
what does not, and the limits of efficiency as a strategy.

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

## Accelerator efficiency claims

Specialised accelerators idle at 30 to 80% of TDP against about 20% for NVIDIA and AMD parts, and
Cerebras reaches H100 energy-per-token parity only above a 34% duty cycle
([024](024-golden-2026-accelerator-competition-idle-power.md)). Applying that test to the
claims held in this folder:

| Claim | What it rests on |
|---|---|
| FPGA at 6.0x a V100S ([003](003-zeng-2024-flightllm-fpga.md)) | batch size 1, against a naive PyTorch baseline; 5.5x against vLLM, 3.8x against an A100, 2.9x against gpt-fast. Margin falls monotonically to batch 64. Runs a sparsified 3.5-bit model at worse perplexity |
| Photonic accelerator ([013](013-hua-2025-photonic-accelerator-ultralow-latency.md)) | 2.38 TOPS/W including lasers, no better than a contemporary GPU. Minimum working latency 5 ns. Workload is Ising max-cut, not inference |
| Silicon neuron ([014](014-pazos-2025-silicon-transistor-neuromorphic.md)) | two 180 nm transistors against 24 in CMOS, two decades behind current logic. Efficiency is comparative against other neuron-mimicking devices |
| Memristive synapse ([006](006-weilenmann-2024-memristor-synaptic.md)) | 36 mJ against 3,464 mJ for a well-utilised A100, a 96x estimate. The 966x headline compares against an under-utilised A100 and is an artefact. No crossbar array was built; the neuron stays on GPU |
| Survey range 3.1x to 10,000x ([016](016-kachris-2025-hardware-accelerators-llm-survey.md)) | 27 accelerators, each against a different baseline; none of the ASIC schemes was fabricated, all simulation at 40 to 55 nm against GPUs at 12 to 16 nm |

None reports a duty cycle against a deployed workload.

## Model choice dominates technique

Image generation draws 2.907 kWh per 1,000 inferences against 0.002 kWh for text classification,
a spread above 1,450x. On extractive question answering a task-specific model emits 0.3 gCO2e
against 10 g for a multi-purpose one ([027](027-luccioni-2024-power-hungry-processing.md)). Model
and task selection move energy further than any serving-stack technique measured here.

Reconfiguring a serving cluster cut measured inference energy 42% against a fixed-configuration
baseline, falling to 23.4% at high load because the saving harvests idle headroom
([012](012-stojkovic-2025-dynamollm-energy-efficient-inference.md)). Most of its economic benefit
is consolidation: $1,362.70/h from renting fewer GPUs against $4.40/h of electricity.

## The limits argument

Compute efficiency does not imply energy efficiency, and neither implies carbon efficiency
([026](026-wright-2025-compute-energy-carbon-efficiency.md)). The measured sign reversals above
are the empirical form of the first gap; the Scope 2 accounting divergence in
[`../washing/`](../washing/) is the second. The paper asserts its rebound argument without
measurement, consistent with the state of that literature.

## Gaps

- No 2026 empirical work on AI rebound effects. Position papers only.
- FP4 on Blackwell is unmeasured. The INT8 penalty above should not be generalised to
  hardware-native FP4.
- Agentic and multi-turn workloads. Per-query studies exclude tool calling by construction.
- MLPerf Power v6.0 and v6.1 publish no summary figures normalised to joules per token.
- No documented case of a classical method matching an LLM at a fraction of the energy. The
  nearest results report accuracy, not joules.
