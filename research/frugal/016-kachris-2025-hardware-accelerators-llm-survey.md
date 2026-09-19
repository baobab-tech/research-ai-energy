# A survey of 27 transformer accelerators finds energy-efficiency claims spanning 3.1x to 10,000x, each against a different baseline, and none of the ASIC results measured on fabricated silicon

**Topic:** Frugal AI — what the accelerator literature's efficiency multipliers are measured against
**Source:** Kachris (University of West Attica, Greece), 2025
**Type:** peer-reviewed
**URL:** https://doi.org/10.3390/app15020586
**Published:** 2025-01

## Finding

Twenty-seven hardware accelerators for transformer workloads published between 2019 and 2024 are
tabulated with their reported speedup, energy-efficiency multiplier and comparison baseline. The
multipliers range from 3.1x to 10,000x, and every one is against a different reference platform:
Xeon and Core CPUs, V100, Titan Xp, GTX 1060, RTX 3090, TPU, ARM A53. The survey's own assessment is that
this makes the schemes incomparable. The largest numbers come from ASIC designs, and the survey states
that none of the proposed ASIC schemes has been implemented in real silicon; all are cycle-accurate
simulations with power estimated by tools such as CACTI, most at 40, 45 or 55 nm nodes. The survey's
conclusion nonetheless asserts that accelerators "can reduce energy requirements in data centers by more
than four orders of magnitude", a claim its own table does not support.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Accelerators surveyed | 27, published 2019-2024 | Literature table; FPGA, GPU, ASIC, in-memory, Flash |
| Range of reported energy-efficiency multipliers | 3.1x to 10,000x | Each against a different baseline; as-reported by original authors |
| Highest claim (Energon, ASIC 45 nm) | 10,000x vs CPU; 1,000x vs V100 GPU | Cycle-accurate simulation, not fabricated |
| SpAtten (ASIC 40 nm) | 4,059x vs Xeon CPU; 1,093x vs Titan Xp GPU | Cycle-accurate simulation |
| ELSA (ASIC 40 nm) | 1,265x vs V100 GPU / TPU | Cycle-accurate simulation |
| ReTransformer (in-memory) | 1,086x vs GPU (unspecified) | Simulation |
| Best FPGA results | 4x to 9.2x | Measured on real hardware; DFX 4x vs V100, ODE 9.2x vs ARM A53, FTRANS 8.8x vs RTX 5000 |
| ASIC implementation status | none fabricated | Stated in Section 7.1: all modelled in cycle-accurate design |
| ASIC process nodes | mostly 40 nm; some 45 nm and 55 nm | Compared against GPUs on 12-16 nm nodes |
| Energon absolute figure | 10 TOPS/W for BERT and GPT-2 | Reported by the original authors |

## Methodology

A literature survey. Each accelerator's reported speedup, energy efficiency and baseline are transcribed
from its source publication into one table; no new measurement is taken and no scheme is re-run on a common
benchmark. The dataset is published at github.com/kachris/survey_HA_LLM. The distinction the survey draws
is between FPGA results, which are implemented and measured on real boards, and ASIC and in-memory results,
which are simulated. Workloads across the surveyed papers are BERT, GPT-2 and GPT-Neo class transformers
rather than the multi-billion-parameter models deployed in 2024-2026.

## Limitations and conflicts

Single author at a Greek public university. The paper states the research received no external funding and
declares no conflicts of interest. No vendor involvement is apparent.

The survey inherits every reported number from its sources without independent verification, and it says so.
The three- and four-order-of-magnitude figures are simulated designs on 40-55 nm nodes compared against
fabricated GPUs on far more advanced nodes; a real chip at those nodes would carry fabrication, memory and
interconnect overheads the simulators do not model.

No entry in the table reports idle power, duty cycle, or a system-level or rack-level measurement. The
numbers are kernel or model-level throughput per joule on an isolated accelerator. The step from that to
the conclusion's claim about data-centre energy is not made anywhere in the paper.

The baseline GPUs are V100 (2017), Titan Xp (2017), GTX 1060 (2016), RTX 5000 (2018) and Volta. Comparison
against the parts that populate current inference fleets does not appear.

## Relation to existing corpus

This is the clearest statement in the corpus that accelerator efficiency multipliers are not comparable to
one another. It sets the context for /research/frugal/003 (FlightLLM, 6.0x on measured FPGA hardware
against a 2019 GPU), which sits near the low, measured end of the range this survey tabulates.
/research/frugal/024 (Golden et al. 2026) supplies what this survey lacks: physical measurement of
deployed accelerators on a common workload, including the idle power and duty-cycle conditions under which
any such multiplier holds.

---
Retrieved: 2026-09-19
Search: DOI 10.3390/app15020586, full text via mdpi-res.com
