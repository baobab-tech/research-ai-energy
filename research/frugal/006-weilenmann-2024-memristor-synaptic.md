# A memristive synapse layer is estimated at 36 mJ per Atari Pong game against 3,464 mJ for a well-utilised A100, a 96x gain that becomes 966x only against an under-utilised GPU

**Topic:** Frugal AI — what an in-memory-computing energy multiplier is measured against, and what falls outside its boundary
**Source:** Weilenmann, Ziogas, Zellweger, Portner, Mladenović, Kaniselvan, Moraitis, Luisier & Emboras (ETH Zurich Integrated Systems Laboratory; Noemon AG), 2024
**Type:** peer-reviewed
**URL:** https://doi.org/10.1038/s41467-024-51093-3
**Published:** 2024-08

## Finding

A single two-terminal SrTiO3 memristor performs all six operations of a short-term Hebbian synapse,
including short-term plasticity, long-term plasticity and decay, without the third gate contact and
external control waveforms that earlier memtransistive implementations required. Substituting these
devices for the synapses of a short-term-plasticity network playing Atari Pong is estimated to consume
36.0 mJ per game against 3,463.9 mJ for an NVIDIA A100 40GB at fp16, a factor of 96. The paper's
alternative figure of 966x compares instead against the same A100 running the network as written, where
169,984 synapses leave the GPU far below its peak efficiency point of roughly 2^21 synapses. The gap
between 96 and 966 is entirely an artefact of GPU utilisation, not of the device. Over 98% of the GPU
energy in this workload is memory traffic, which is the quantity in-memory computing removes.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Memristor synaptic energy, one Pong game | 36.0 mJ | Estimated from measured single-device behaviour, extrapolated over 169,984 synapses |
| A100 fp16, scaled to peak efficiency point | 3,463.9 mJ | "GPU (optimal)": measured at ~2^21 synapses, scaled down to 169,984 |
| A100 fp16, network as written | 34,780.5 mJ | "GPU (standard)": measured at the network's actual 169,984 synapses |
| A100 fp32, as written / scaled | 34,932.3 mJ / 6,292.0 mJ | Same two boundaries |
| Resulting multiplier | 96x (vs optimal) to 966x (vs standard) | Division of the above; the paper's own discussion states "at least 96" |
| Memristor energy composition | Decay bias 35.6 mJ of 36.0 mJ total; ΔF updates 0.4 mJ | Decay assumes worst case Vbias = 0.6 V applied to every synapse |
| Idle power per synapse at G = 0 | 4.3 nW | Measured, Vbias = 0.6 V |
| Share of GPU energy that is memory traffic | >98% | Quantified by the authors in Methods |
| Device | Cr-Pt and Ti-Pt planar electrodes on SrTiO3 single crystal, ~40 nm electrode gap, 15-30 nm SiN encapsulation | E-beam lithography and evaporation; individual lab devices, no CMOS node, no crossbar array |
| Network | STPN layer, 169,984 synapses, Atari Pong reinforcement learning | Synapses only |

## Methodology

Individual memristors were fabricated on an SrTiO3 single crystal by e-beam lithography and electrically
characterised to extract energy per programming pulse as a function of pulse voltage and width. Those
measurements were fed into a network simulator that replayed a trained STPN agent through a full game of
Pong and summed the per-synapse energy. The GPU side is direct measurement on an A100 40GB, median of 100
runs per synaptic operation at fp16 and fp32. The memristor side is not a circuit simulation: the authors
state that a full circuit encompassing the whole network would raise the memristive figure, and that a
crossbar array configuration, which was not built, is necessary to perform the vector-matrix
multiplication the comparison credits to the device.

## Limitations and conflicts

The comparison covers synaptic operations only. The neuron operations remain on a GPU in both cases,
specifically the magnitude of the short-term update, the non-linear activation and the pre-synaptic input
normalisation, as do the convolutional feature extractor and the fully-connected actor and value layers.
No system-level energy per inference is reported, so the 96x does not propagate to the whole agent. The
device is a planar single-crystal laboratory structure, not a CMOS-integrated process, and the authors
list the moves still required for hardware realisation: conversion to vertical structures, improved
long-term retention, and reduced device-to-device variability. Peripheral circuitry, analogue-to-digital
conversion and array parasitics are excluded. The workload is Atari Pong, not any deployed AI service.
Funding is ETH Zurich and Swiss public sources; one author is affiliated with Noemon AG, and no
commercial device interest is disclosed in the record retrieved.

## Relation to existing corpus

Confirms the pattern documented in file 016 (Kachris 2025), where 27 accelerator efficiency multipliers
spanning 3.1x to 10,000x each rest on a different baseline. Here both baselines are in the same paper and
differ by a factor of 10 purely through GPU utilisation, which makes the mechanism explicit. The
utilisation dependence matches file 024 (Golden 2026), where accelerator advantage is conditional on
duty cycle, and the memory-traffic share above 98% matches the memory-bound decode regime in file 021
(Delavande 2026) that defeats precision reduction on a GPU.

---
Retrieved: 2026-09-19
Search: Crossref DOI lookup, then full text PDF from nature.com (open access, pdftotext)
