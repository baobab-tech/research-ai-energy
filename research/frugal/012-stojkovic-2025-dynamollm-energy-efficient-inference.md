# Reconfiguring an H100 serving cluster cut measured LLM inference energy 42% over a fixed-configuration baseline, with headline savings of 53% reported from simulation

**Topic:** Frugal AI — energy saved by scheduling and frequency control in a production LLM serving cluster
**Source:** Stojkovic & Torrellas (University of Illinois Urbana-Champaign) with Zhang, Goiri & Choukse (Microsoft Azure Research - Systems), 2025
**Type:** peer-reviewed
**URL:** https://doi.org/10.1109/HPCA61900.2025.00102
**Published:** 2025-03

## Finding

Serving energy falls substantially when a cluster varies GPU clock frequency, tensor-parallel width and
instance count with the shape of the incoming request instead of holding one configuration. Profiling
Llama2-70B on NVIDIA DGX H100 servers under vLLM shows energy per request varying by more than 10x across
request length, parallelism and frequency, and the energy-optimal configuration is neither the
lowest-power one nor the highest-performance one. Against SinglePool, a baseline that routes every request
to one pool running tensor parallelism across 8 GPUs at the maximum 1980 MHz clock, a 24-hour run on 11
H100 servers with Azure production traces measured a 42% energy reduction. The abstract and conclusion
report 53% energy, 38% operational carbon and 61% cost; no single experiment in the paper produces those
three numbers, and the nearest in-text energy figures are 47% and 56% from a discrete-time simulator.
Savings collapse as the cluster fills: 51% at low load, 40% at medium, 23.4% at high.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Energy reduction vs SinglePool, 24 h | 42% | Measured, 11 servers of 8x H100, Llama2-70B, Azure Conversation trace |
| Energy reduction, 1-week traces | 47% (Conversation), 56% (Coding) | Discrete-time simulator, not hardware |
| Headline energy / carbon / cost | 53% / 38% / 61% | Abstract and conclusion; not reproduced by any single in-text experiment |
| Energy reduction by load level | 51% low, 40% medium, 23.4% high | Poisson synthetic inter-arrival times; saving shrinks as SLO slack disappears |
| Operational CO2, week of conversation traces | 5.0 t → 3.1 t (38%) | CAISO grid carbon-intensity trace applied to modelled energy |
| GPU servers provisioned | 40 → 24.6 average (38.5%) | Consolidation accounts for part of the saving |
| Cost saving composition | $1362.7/h from fewer GPU VMs; $4.4/h from energy | Energy is a negligible share of the cost saving |
| Cluster power reduction | P50 43%, P99 9% | Per-cluster and per-GPU power traces |
| Latency cost | P99 TTFT -5.3%, P99 TBT -11.1%; P50 TTFT +11.4%, P50 TBT +7.6% | Median latency worsens; SLOs still met |
| Energy per request, Llama2-70B, 2K tokens/s | 0.77 Wh (short/short, TP2 @1.2 GHz) to 13.21 Wh (long/long, TP8 @2.0 GHz) | Measured on DGX H100 under vLLM |
| Output-length mispredictions | 40% error rate raises energy 13%, TTFT 7.3% | Sensitivity study |
| Reconfiguration overhead | ~50 ms to move 1/8 of Llama2-70B over 300 GB/s NVLink | Measured re-sharding cost |

## Methodology

Energy and latency were profiled directly on NVIDIA DGX H100 servers running vLLM, sweeping GPU frequency
from 800 to 1980 MHz in 200 MHz steps across tensor parallelism of 2, 4 and 8, for Llama2-13B,
Llama2-70B, Llama3-70B, Mixtral-8x7B, Mixtral-8x22B and Falcon-180B. Requests were bucketed into nine
classes by input and output length using the 33rd and 66th percentiles of an Azure conversation trace,
with SLOs set at 5x the isolated single-request latency. A mixed-integer linear program selects instance
count, parallelism and frequency, decomposed into a hierarchy of controllers acting at 30-minute,
5-minute and 5-second intervals. Load came from open-source 1-hour traces and from 1-day and 1-week
Azure Coding and Conversation traces. The 24-hour result is hardware measurement; the 1-week results are
produced by a discrete-time simulator calibrated on the profiles. Carbon is modelled by multiplying
energy against a CAISO carbon-intensity trace.

## Limitations and conflicts

Three of the five authors are Microsoft Azure Research staff and the production traces come from
Microsoft's own fleet, so the workload cannot be independently reproduced. The baseline is chosen by the
authors and is deliberately unoptimised: one pool, maximum clock, widest parallelism, no autoscaling.
Part of the reported saving is consolidation onto fewer GPUs rather than any gain in energy per token,
which the cost breakdown makes explicit, with GPU rental accounting for $1362.7/h of saving against $4.4/h
from electricity. The headline 53% and 61% figures are not derived anywhere in the text. Carbon savings
are modelled, not metered, and depend on the CAISO intensity profile; a flatter grid would yield less
than 38%. Energy accounting covers GPUs; server, cooling and facility overhead are outside the boundary,
so the cluster-level saving does not translate one-for-one into facility energy. Scope is inference only.
Numbers here were verified against the full text at arXiv:2408.00741; the HPCA version of record was not
retrievable and may differ in detail.

## Relation to existing corpus

Consistent with file 021 (Delavande 2026), which finds request arrival shaping and batching quality
dominate serving energy while numerical precision often does not, and with file 024 (Golden 2026), where
idle power at low duty cycle is the controlling term. The load sensitivity here sharpens both: the
saving comes from exploiting SLO slack and idle headroom, so it falls to 23.4% once the cluster is busy.
This bounds the claim in file 025 (Chung 2026) that scheduling choices swing measured energy widely, by
showing the swing is largest exactly where utilisation is lowest.

---
Retrieved: 2026-09-19
Search: Crossref DOI lookup, then full text of arXiv:2408.00741 (PDF, pdftotext)
