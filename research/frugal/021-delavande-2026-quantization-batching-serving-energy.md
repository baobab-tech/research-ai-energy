# INT8 quantisation raised decode energy 2–3x over FP32 on an H100; request arrival shaping cut per-request energy up to 100x

**Topic:** Frugal AI — measured energy effects of the deployed serving stack (precision, batching, scheduling)
**Source:** Delavande (Hugging Face / ENS Paris-Saclay), Pierrard & Luccioni (Hugging Face), 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2601.22362
**Published:** 2026-01-29

## Finding

Measured on a dedicated NVIDIA H100 SXM 80GB, lower numerical precision reduces energy only where the
workload is compute-bound. In prefill on larger models, moving from FP32 to FP16/BF16/INT8 cut GPU energy
up to 4x. In decode — memory-bound at all model sizes and sequence lengths tested — energy per generated
token was largely invariant across FP32, FP16 and BF16, and INT8 consumed **2–3x more** energy than FP32
because on-the-fly dequantisation adds small, fragmented, irregular kernels while the GPU's ~120 W idle
floor keeps burning during the gaps. INT4 landed at roughly FP32 parity. Batching and, more strongly,
structured request timing dominated: arrival shaping reduced per-request energy by up to 100x.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Prefill, FP32 → FP16/BF16/INT8, large models | up to 4x GPU energy reduction | H100 SXM 80GB, measured via CodeCarbon (NVML) |
| Decode, FP32 vs FP16 vs BF16 | energy per output token largely invariant | Memory-bound regime |
| Decode, INT8 vs FP32 | INT8 often 2–3x *more* energy | bitsandbytes LLM.int8() post-training quantisation |
| Decode, INT4 vs FP32 | approximately parity | NF4, weights packed two per byte |
| Latency improvement where energy did not follow | up to 10x lower latency in large models | Faster completion at higher instantaneous power |
| GPU idle power during decode gaps | ~120 W | Explains why shorter kernels do not save energy |
| Arrival shaping (request scheduling) | up to 100x lower per-request energy | Varying traffic patterns, batching quality |
| Theoretical bandwidth-limited expectation | 2x (FP32→FP16), 4x (FP32→INT8) | Not observed in practice |
| Models | Qwen 2.5 at 0.5B / 1.5B / 3B / 7B / 14B; Llama 3.1-8B-Instruct | HF Transformers; TGI for serving configuration |

## Methodology

Direct measurement, not modelling. GPU energy via CodeCarbon using NVML, CPU via pyRAPL, RAM estimated by
a CodeCarbon heuristic; hardware is one dedicated H100 SXM 80GB with 8 AMD EPYC cores. Five numerical
precisions (FP32, FP16, BF16, INT8, INT4), batch-size sweeps, and traffic-pattern experiments with Hugging
Face Text Generation Inference. Energy per input token is reported both on effective tokens (excluding
padding) and computed tokens (including padding), which matters because padding inflates the apparent
efficiency of large batches.

The boundary is GPU (plus CPU/RAM estimates) on a single node. No PUE, no datacenter overhead, so these
numbers are not comparable in level to /research/frugal/017 — only in ratio.

An important caveat the authors state: runs use HF Transformers static batching for the batch-size study,
not a continuous-batching production server, so the absolute decode numbers reflect a research stack. The
mechanism identified (idle power between fragmented kernels) is general; the magnitude is stack-specific.

## Limitations and conflicts

Two of three authors are employed by Hugging Face, which publishes the AI Energy Score — a benchmark that
/research/frugal/017 (Microsoft) singles out as producing 4–20x overestimates. This paper is in part the
methodological defence of that position: it argues the serving stack, not the model, dominates. Neither
side is disinterested.

Single-GPU only; no multi-node, no tensor parallelism, no MoE, no speculative decoding. bitsandbytes is
one quantisation implementation among several and is not what production stacks use for FP8 on Hopper —
the INT8 penalty reported here should not be generalised to hardware-native FP8 or to FP4 on Blackwell,
which have dedicated tensor-core paths and no dequantisation kernels.

## Relation to existing corpus

No direct overlap; the corpus had no measured serving-stack energy at all. It qualifies the blanket claim
that quantisation reduces energy, which holds only in the compute-bound part of the workload. Luccioni
also authors /research/frugal/027-luccioni-2024-power-hungry-processing.md.

---
Retrieved: 2026-09-19
Search: arXiv abs:"quantization" AND abs:"energy" AND abs:"LLM inference", sortBy=submittedDate
