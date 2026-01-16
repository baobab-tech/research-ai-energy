# FlightLLM: FPGA-Based Efficient LLM Inference

**Topic:** Frugal AI - Efficient Architectures
**Source:** Zeng, Liu, Dai et al., 2024
**URL:** https://doi.org/10.1145/3626202.3637562

## Insight

FlightLLM demonstrates that specialized hardware (FPGAs) can run large language models with dramatically improved energy efficiency compared to GPUs. By utilizing FPGA-specific resources and compression techniques like sparsification and quantization, the system achieves 6x better energy efficiency than commercial GPUs while maintaining competitive throughput. This proves that hardware-algorithm co-design can substantially reduce AI's environmental footprint.

## Key Data

- Energy efficiency: 6.0x higher than NVIDIA V100S GPU on LLaMA2-7B workload
- Cost efficiency: 1.8x better than commercial GPUs for batch-one inference
- Throughput: 1.2x higher than NVIDIA A100 GPU using latest Versal VHK158 FPGA
- Techniques used: Configurable sparse DSP chain, always-on-chip decode scheme, mixed-precision quantization support
- Compression: Sparsification and quantization mitigate computation/memory overhead gap

## Notes

- Published at FPGA 2024 (ACM/SIGDA International Symposium) - top venue for FPGA research
- 86 citations as of January 2025 - highly influential in efficient AI hardware space
- Authors from Tsinghua University and other Chinese institutions
- Demonstrates real-world deployment on Xilinx Alveo U280 FPGA platform
- Key insight: GPUs are inefficient for compressed/sparse LLMs - specialized hardware needed
- Addresses "unresolved challenges" of low computational efficiency and underutilized memory bandwidth on GPUs

---
Retrieved: 2026-01-16
Search: OpenAlex "FlightLLM FPGA inference"
