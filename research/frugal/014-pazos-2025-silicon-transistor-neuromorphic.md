# Two standard 180 nm transistors reproduce neuron and synapse behaviour where CMOS circuits need 24, at a firing energy of 415 pJ per micrometre and with no neural network built

**Topic:** Frugal AI — device-level neuromorphic research and its distance from deployed energy savings
**Source:** Pazos, Zhu, Villena, Alharbi, Zheng, Shen, Yuan, Ping & Lanza (King Abdullah University of Science and Technology; National University of Singapore), 2025
**Type:** peer-reviewed
**URL:** https://doi.org/10.1038/s41586-025-08742-4
**Published:** 2025-03

## Finding

An n-type MOSFET biased into the punch-through regime with a floating bulk reproduces leaky-integrate-and-
fire behaviour, and a second transistor in series makes a 2-transistor cell that switches between neural
and synaptic modes. Conventional CMOS needs at least 18 transistors per neuron and six per synapse. Yield
is 100% and device-to-device variability is low because the devices are standard commercial CMOS with no
exotic materials. The devices measured are 180 nm and 500 nm parts, nodes two decades behind current logic,
and firing energy is 415 pJ per micrometre of channel width. No artificial neural network was built. The
authors state that for every prior neuro-synaptic device technology, at least seven years separated the
first device demonstration from the first hardware ANN, and that for some technologies it has still not
happened.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Transistors per combined neuron and synapse | 2 | Cell design; CMOS baseline is >=18 per neuron plus >=6 per synapse |
| Firing energy | down to 415 pJ per micrometre of channel width | Measured at constant drain voltage, 180 nm device |
| Technology node | 180 nm (3.5 nm oxide) and 500 nm (10 nm oxide) bulk silicon MOSFETs | Standard commercial CMOS |
| Yield | 100% | Measured across the devices characterised |
| Switching slope | below 10 mV/decade | Measured |
| Dynamic range | over 10^3 | Measured current range |
| Endurance | over 10 million cycles (180 nm, pulsed 10 us on / 60 us relax); >70,000 cycles (500 nm) | Measured |
| Synaptic weight levels | at least 6 stable levels; up to 14 distinct levels over >700,000 potentiation/depression cycles | Measured |
| Firing time tuning range | 10 us to 2 ms for V_spike 3.5-4.5 V | Measured, V_G 0.35-0.45 V |
| Neural network demonstrated | none | The paper reports device and circuit measurements only |

## Methodology

Devices are standard polysilicon/SiON gate-stack bulk-silicon MOSFETs from a commercial CMOS line,
characterised on a probe station with custom electrodes. Quasi-stationary I-V, fast voltage ramps up to
80,000 V/s, and pulsed firing regimes were measured. The physics was cross-checked with Sentaurus TCAD
simulations of impact ionisation and hot-carrier injection, calibrated against the measurements, and with
an open-source SPICE model of the avalanche regime. Die-to-die variation in the effective bulk resistance
was traced to wafer position across 30 dice from a multi-project wafer, which the second transistor in the
cell controls for.

## Limitations and conflicts

Funded by KAUST baseline funding and an NUS startup fund. The authors declare no competing interests. No
industry funding is disclosed.

The energy claim is comparative against other neuron-mimicking devices, not against digital CMOS running
a neural network. 415 pJ per micrometre at a 180 nm node is large in absolute terms; a digital multiply-
accumulate on a current logic node costs femtojoules. Whether the density advantage survives migration to
a modern node is untested, and the paper offers no projection.

Nothing here has been assembled into a working network, in hardware or in simulation, and no task accuracy
or system-level energy figure exists. The authors describe the result as a short-term solution and note the
peripheral circuitry needed to move from a device to an ANN is substantial. The paper's own seven-year
precedent makes it a research result rather than a near-term route to lower data-centre energy.

Neuromorphic computing addresses spiking networks, which are not the architecture of the transformer
workloads driving data-centre demand.

## Relation to existing corpus

No direct overlap. The corpus contains no other device-level neuromorphic source, and this file's value in
a frugal-AI collection is as a marker of how far pre-deployment the neuromorphic efficiency argument sits.
The duty-cycle test in /research/frugal/024 cannot even be applied here, because there is no system to
measure.

---
Retrieved: 2026-09-19
Search: DOI 10.1038/s41586-025-08742-4, full text at nature.com
