# A 16,000-component photonic accelerator measures 2.38 TOPS/W including lasers, which is no better than a contemporary GPU; its demonstrated advantage is latency, not energy

**Topic:** Frugal AI — whether photonic computing delivers measured energy savings over electronic accelerators
**Source:** Hua, Divita, Yu, Peng, Su, Chen, Meng, Steinman & Shen et al. (Lightelligence Pte. Ltd., with Stanford University), 2025
**Type:** peer-reviewed
**URL:** https://doi.org/10.1038/s41586-025-08786-6
**Published:** 2025-04

## Finding

The PACE photonic accelerator integrates more than 16,000 photonic components on one chip and runs a
64x64 optical matrix multiply-accumulate engine at a 1 GHz clock. Measured energy efficiency is 4.21
TOPS/W excluding the laser sources and 2.38 TOPS/W including them, against a measured throughput of about
8.19 TOPS. Those figures sit in the same range as INT8 throughput per watt on data-centre GPUs of the same
period, so the paper does not demonstrate an energy advantage over electronics. What it does demonstrate is
latency: solving a max-cut Ising problem took 2.7 microseconds on PACE against 798.1 microseconds on an
NVIDIA A10 GPU, roughly two orders of magnitude. The workload is combinatorial optimisation by a heuristic
recurrent algorithm, not neural network training or inference.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Energy efficiency including lasers | 2.38 TOPS/W | Measured, full PACE system |
| Energy efficiency excluding lasers | 4.21 TOPS/W | Measured, photonic and electronic ICs only |
| Throughput | ~8.19 TOPS | Measured, 64x64 optical MAC at 1 GHz |
| Photonic components | >16,000 on one chip | Count, 2.5D hybrid packaged PIC plus EIC |
| Minimum working loop latency | 5 ns | Measured; convergence >92.72% over ten batches of 2,000 Ising tests |
| Latency at 2 ns | convergence falls below 25% | Measured; the algorithm stops working |
| 3 ns latency | stated as achievable in future devices | Projection, not measured |
| Configurable loop latency range | 1-26 ns | Measured system parameter |
| Computation accuracy | 7.61-bit average ENOB; 8-bit for >65% of channels | Measured over 30,000 random dot products at 25 MHz |
| Total time to solution vs GPU | 2.7 us (PACE) vs 798.1 us (NVIDIA A10) | Measured; same heuristic algorithm, 63x63 max-cut |
| Iterations to solution | 537 (PACE) vs 347 (A10 GPU) | Measured averages; PACE needs more iterations, each far faster |

## Methodology

A photonic integrated circuit is 2.5D hybrid packaged with an electronic IC carrying the logic, memory,
DACs, drivers and control. Vector modulators are 64 Mach-Zehnder units at 1 GHz with non-return-to-zero
modulation; weight modulators run at 10 MHz with higher bit resolution because Ising weights are fixed per
problem. Accuracy is characterised as effective number of bits over random dot products. The application
benchmark is an Ising model solved by a heuristic recurrent algorithm, run as a 63x63 max-cut and a 64x64
image-derived adjacency problem. The GPU comparison runs the same algorithm on an NVIDIA A10 with noise
added in the digital domain; on the GPU the iteration and energy calculation run sequentially, while PACE
computes energy in a dedicated parallel circuit.

## Limitations and conflicts

Every author except the Stanford co-authors is employed by Lightelligence Pte. Ltd., a photonic computing
company commercialising this technology, and the competing interests statement discloses two granted US
patents (11,734,555 B2 and 11,907,832 B2) covering related work. The paper is a demonstration of a
company's own product.

The comparison GPU is an NVIDIA A10, a 150 W inference card released in 2021, and the comparison is of
latency and time to solution only. No energy-per-solution comparison against any GPU is reported, so the
two-orders-of-magnitude figure says nothing about energy. Reading it as an energy result is the error the
paper's own numbers rule out: 2.38 TOPS/W is not a large number.

The matrix is 64x64 and the arithmetic is analogue at under 8 effective bits. Nothing in the paper
addresses transformer inference, training, or any workload of the kind that drives data-centre demand.
System idle power and duty cycle are not reported, and the laser sources run continuously whether or not
computation is in progress, which is the property that separates the 4.21 and 2.38 TOPS/W figures.

The system requires preliminary calibration and tolerates only about +/-5 degrees C of ambient variation
without active feedback control.

## Relation to existing corpus

The idle-power and duty-cycle test applied in /research/frugal/024 (Golden et al. 2026) bears directly on
this system: the 1.8x gap between the with-laser and without-laser efficiency figures is a continuously
drawn overhead of the same kind, and the paper reports no duty cycle. The corpus has no other measured
energy figure for photonic computing.

---
Retrieved: 2026-09-19
Search: DOI 10.1038/s41586-025-08786-6, full text at nature.com
