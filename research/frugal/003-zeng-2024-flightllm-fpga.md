# FlightLLM on an Alveo U280 FPGA reaches 6.0x the tokens per joule of a 2019 NVIDIA V100S at batch size 1, and the margin shrinks as batch size rises

**Topic:** Frugal AI — measured energy efficiency of FPGA LLM inference against GPU baselines
**Source:** Zeng, Liu, Dai, Yang, Fu, Wang, Ma, Sun, Li, Huang, Dai, Li, Wang, Zhang, Wen, Ning & Wang (Tsinghua University, Shanghai Jiao Tong University, Infinigence-AI), 2024
**Type:** peer-reviewed
**URL:** https://doi.org/10.1145/3626202.3637562
**Published:** 2024-01

## Finding

An FPGA accelerator running a compressed LLaMA2-7B delivers 6.0x the tokens per joule of an NVIDIA
V100S running the uncompressed model in HuggingFace PyTorch, at batch size 1. The margin depends on
which baseline is chosen: against a V100S running vLLM plus SmoothQuant it is 5.5x, against an A100
running the same optimised stack 3.8x, and against an A100 running gpt-fast 2.9x. The V100S is a 2019
part on a 12 nm process; the A100 is 2020 on 7 nm. The comparison is not like-for-like on model quality:
FlightLLM runs a sparsified, 3.5-bit-weight model whose WikiText-103 perplexity is 10.2 against 8.7 for
the uncompressed model. The authors report that the advantage over GPUs falls as batch size rises from 1
to 64, because GPUs have more memory bandwidth and higher clock frequency to bring to bear.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Energy efficiency, LLaMA2-7B, batch 1 | 6.0x V100S-naive; 5.5x V100S-opt; 4.4x A100-naive; 3.8x A100-opt | Tokens/J, geomean over six prefill/decode length pairs; FPGA board power via Xilinx xbutil, GPU power via nvprof |
| Energy efficiency, OPT-6.7B, batch 1 | 6.7x V100S-naive; 6.0x V100S-opt; 4.6x A100-naive; 4.2x A100-opt | Same method |
| Energy efficiency vs gpt-fast on A100 | 2.9x | LLaMA2-7B, batch 1, VHK158 (simulated FPGA) |
| Cost efficiency | 1.8x vs V100S, 1.4x vs A100 (geomean, both models) | Tokens/s/dollar at list prices: V100S ~$12,000, A100 ~$17,000, U280 ~$8,000 |
| Throughput vs A100 | 1.2x | Versal VHK158 FPGA, cycle-accurate simulation, not measured silicon |
| Model compression | 3.5-bit weights average, 8-bit activations, block-sparse attention, N:M weight pruning | Applied to the FPGA model only |
| Perplexity cost of compression, LLaMA2-7B | WikiText-103: 8.7 to 10.2; WikiText-2: 21.2 to 21.9 | Measured after finetuning on 56M tokens of RedPajama |
| Batch-size sensitivity | Advantage over GPU decreases monotonically from batch 1 to batch 64 | Measured, LLaMA2-7B, U280 vs GPU-opt |
| Hardware utilisation on U280 | 70.2% of DSPs, 82.5% of URAM, 62.1% of BRAM, 44.0% of LUTs | Implementation report, 225 MHz kernel clock |

## Methodology

FlightLLM is implemented in RTL on a single Xilinx Alveo U280 card and measured on a real server. Board
power comes from the vendor tool xbutil; GPU power from nvprof at runtime. Baselines are two GPUs at two
software levels each: HuggingFace PyTorch as "naive", and vLLM plus SmoothQuant INT8 as "opt", with a
further gpt-fast comparison at batch 1. Workloads are LLaMA2-7B and OPT-6.7B at six prefill/decode length
combinations from [128,512] to [512,1536]. Unless stated otherwise every result is at batch size 1, chosen
to represent latency-sensitive serving. The second FPGA platform, Versal VHK158, is not measured: its
numbers come from a cycle-accurate simulator verified against RTL emulation.

## Limitations and conflicts

Eight of the seventeen authors list Infinigence-AI, an AI infrastructure company, alongside or instead of a
university affiliation; the work is funded by the National Natural Science Foundation of China and the
Beijing National Research Center for Information Science and Technology. No FPGA vendor funding is
declared.

The energy comparison holds a compressed model against uncompressed and INT8 models, so part of the 6.0x
is the compression rather than the silicon. The authors note the compression methods are compatible with
GPUs but need FPGA-specific units to convert into wall-clock speedup, which concedes that a portion of the
gain is attributable to the algorithm.

No idle power, standby power, or duty cycle is reported for the U280, and no deployed workload trace is
used. The measurement is a single card running one model at batch size 1 with the accelerator busy. Serving
energy depends on what the part draws between requests, which is not measured here, so the figure cannot be
converted into an energy saving for a deployed service. The batch-size result points the same way: at the
batch sizes production inference actually uses, the reported gap closes.

Both GPU baselines predate the paper by four and five years. The parts that dominate 2024-2026 inference
fleets, H100 and after, are not compared.

## Relation to existing corpus

The efficiency figure is exactly the kind of claim quantified by /research/frugal/024 (Golden et al. 2026),
which measures idle power on seven accelerator families and finds specialised silicon idling at 30-80% of
TDP against 20% for NVIDIA GPUs, with Cerebras reaching energy-per-token parity against 32 H100s only above
a 34% duty cycle. FlightLLM reports no duty cycle, so its 6.0x is an upper bound that holds only at
continuous full load.

---
Retrieved: 2026-09-19
Search: DOI 10.1145/3626202.3637562; full text via arXiv:2401.03868
