# MoE sparsity did not deliver its FLOP advantage in energy: an MoE with 1.3B active parameters used 2.1x the energy per token of a dense 1B model on edge hardware

**Topic:** Frugal AI — whether sparse activation reduces energy in practice
**Source:** Alfarizy, Nguyen, Richard, Razavi-Far & Cao (University of New Brunswick, Canada), 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2606.21428
**Published:** 2026-06-19 (v3 2026-07-09)

## Finding

OLMoE-1B-7B (1.3B active of 6.9B total) was benchmarked against dense baselines on an Apple M2 Pro and an
NVIDIA Jetson Orin Nano 8GB through llama.cpp with on-device energy measurement. The per-token FLOP
advantage of sparse activation did not survive: on the laptop OLMoE ran ~10% behind Llama-3.2-1B (the
same active-parameter count), and on the Jetson ~31% behind at **2.1x the energy per token**, with peak
memory at the 8GB ceiling. Instrumenting the decode graph node by node showed routing accounts for under
9% of MoE-block compute, so the gap is total-parameter memory footprint, expert dispatch and KV-cache
pressure — on bandwidth-bound hardware, inference cost tracks total parameters, not active ones.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| OLMoE-1B-7B vs Llama-3.2-1B, Apple M2 Pro | ~10% lower throughput | llama.cpp, on-device energy measurement |
| OLMoE-1B-7B vs dense baseline, Jetson Orin Nano 8GB | ~31% lower throughput, 2.1x energy per token | Same |
| Routing share of MoE-block compute | <9% | Node-by-node decode-graph timing on the edge backend |
| Peak memory, Jetson | at the 8GB ceiling | Total parameters 6.9B, not active 1.3B, set the footprint |
| Models | OLMoE-1B-7B vs three dense baselines | One MoE model, one parameter scale |
| Harness | https://github.com/Analytics-Everywhere-Lab/edge-moe | Per-run data released |

## Methodology

On-device power measurement on two real devices rather than FLOP accounting. The diagnostic step —
patching llama.cpp to time each node of the decode graph — is what turns the result from a benchmark
number into a mechanism: it rules out router overhead as the explanation and points at memory bandwidth
and weight residency. That mechanism generalises to any bandwidth-bound deployment; the magnitude does
not necessarily.

## Limitations and conflicts

The authors state the bound themselves: one MoE model at one parameter scale, two devices. llama.cpp is
not a production serving stack and does not implement the expert-parallel placement, expert offloading or
batched dispatch that datacenter MoE serving uses, where many concurrent tokens amortise the weight reads
that dominate here. The finding should be read as "sparse activation does not buy back what a
bandwidth-constrained single-stream device is short of", not as evidence that MoE is inefficient in
datacenter serving — where the opposite is reported (see the MoE tokens-per-watt figures in
arXiv:2603.17280, which are analytical rather than measured). Academic authors, no industry funding
disclosed.

## Relation to existing corpus

No direct overlap. It is the corpus's first measured test of an efficiency claim made on FLOP grounds,
and it fits the pattern established by /research/frugal/021 and /research/frugal/022: efficiency
techniques validated on a proxy metric (FLOPs, latency) do not reliably transfer to joules.

---
Retrieved: 2026-09-19
Search: arXiv abs:"quantization" AND abs:"energy" AND abs:"LLM inference"; abs:"tokens per joule"
