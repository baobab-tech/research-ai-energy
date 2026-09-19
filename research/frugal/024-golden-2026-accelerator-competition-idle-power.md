# Measured across seven accelerator families, no platform wins on energy across all workloads, and specialised silicon idles at 30–80% of TDP

**Topic:** Frugal AI — measured perf-per-watt of deployed AI accelerators; the utilisation condition on efficiency claims
**Source:** Golden, Wei & Brooks (Harvard University) with Wu (FAIR at Meta), 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2604.10852
**Published:** 2026-04-12

## Finding

Physical power and performance measurements on Cerebras CS-3, SambaNova SN-30/SN-40, Groq, Intel Gaudi and
Google TPUv5e, compared against NVIDIA A100/H100 and AMD MI-300X, find no accelerator dominant across the
design space: the optimal platform changes with batch size, sequence length and model scale. Idle power
separates general-purpose from specialised silicon sharply — 20% of TDP for NVIDIA GPUs and MI300, 30%
for Gaudi, 40% for SambaNova, 80% for Cerebras. Cerebras reaches energy-per-token parity with a 32-GPU
H100 cluster only above a 34% duty cycle. Advantages measured in isolation can disappear once scale-out
communication is included: Groq is Pareto-optimal on decode under a zero-communication assumption and
loses that position when real inter-chip communication is counted.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Idle power as share of TDP | NVIDIA A100/H100 and AMD MI300: 20%; Gaudi: 30%; SambaNova: 40%; Cerebras: 80% | Measured on physical hardware |
| Decode power as share of prefill power | NVIDIA 50–60%; SambaNova 75%; Cerebras 100% | Power traces, Llama-3.1-8B |
| Decode power as share of TDP | NVIDIA and Gaudi 45–60%; SambaNova and MI300 75–80%; Cerebras 100% | Memory-bound decode |
| Cerebras break-even vs 32x H100 | energy-per-token parity at 34% duty cycle | Below that, the idle penalty dominates |
| Low-batch latency per token, Llama-3.1-8B (H100 = 100%) | Cerebras 22.9%, Groq 30.0%, SN-40 48.6% | Small model, small batch; SN-40 and Groq via API |
| On-wafer vs off-chip communication | CS-3 uses 34,454x less J/byte than H100 over 161 mm; 2.74x less than Groq | Microbenchmark; only while the model fits one wafer |
| Groq scale-out | Pareto-optimal on decode at zero exposed communication; loses it with realistic communication | Distributed inference for large models |

## Methodology

Empirical measurement on the physical racks where available, supplemented by vendor APIs where physical
access or batch-size scaling was unsupported (SN-40, Groq). Power telemetry is built in for NVIDIA, AMD
and Gaudi; Cerebras and SambaNova required custom scripts, so measurement fidelity is not uniform across
platforms. Idle, peak and phase-resolved (prefill vs decode) power were recorded per platform. Distributed
scale-out results are reported in two variants: an optimistic case assuming zero exposed communication
latency and a realistic case including it.

Power measurements for SambaNova use SN-30 rather than the SN-40 generation quoted elsewhere in the paper,
because SN-30 is the only rack the authors had physical access to.

## Limitations and conflicts

Carole-Jean Wu is at FAIR (Meta), a company that both buys accelerators at scale and designs its own; the
other three authors are Harvard. Vendor-supplied software stacks differ enormously in maturity, and the
authors report that incomplete kernel coverage and undocumented limitations repeatedly constrained what
could be run — meaning some platforms are measured on less favourable configurations than their vendors
would choose. Batch-size scaling was not supported on the physical CS-3 and Groq setups, which limits the
throughput range explored for exactly the platforms whose efficiency claims depend on it. TPUv5e and
Gaudi1 are prior-generation parts.

The paper measures accelerators, not racks: it does not address whether absolute power per rack is rising.
That distinction has to be sourced separately.

## Relation to existing corpus

No direct overlap; the corpus had no measured comparison of deployed AI accelerators. It is the
counterweight to /research/frugal/003 (FlightLLM FPGA, 6x over a V100S), /research/frugal/013 (photonics)
and /research/frugal/016 (accelerator survey): all of those report efficiency for specialised hardware
under favourable conditions, and this paper quantifies the condition — specialised silicon carries a
30–80%-of-TDP idle penalty and only pays back at high duty cycle. The Cerebras 34% break-even is the
single most transferable number for judging any "Nx more efficient than a GPU" claim in the folder.

---
Retrieved: 2026-09-19
Search: arXiv abs:"H100" AND abs:"energy" AND (abs:"B200" OR abs:"Blackwell" OR abs:"A100")
