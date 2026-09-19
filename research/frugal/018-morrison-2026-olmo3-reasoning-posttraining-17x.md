# Post-training a reasoning model cost 17x the datacenter energy of its instruction-tuned twin; 82% of total compute was never-released development

**Topic:** Frugal AI — where the energy of a reasoning model actually goes; completeness of environmental reporting
**Source:** Morrison (U. Washington / Allen Institute for AI), Smith (UW / Ai2), Strubell (Carnegie Mellon), 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2605.01158
**Published:** 2026-05-01

## Finding

Measured per-GPU power telemetry across the full Olmo 3 development pipeline shows that post-training the
32B reasoning variant (Think) consumed 98,464 kWh of datacenter energy against 5,659 kWh for the 32B
instruction variant — a factor of 17.4 — with 87% of the Think-specific post-training energy going to
reinforcement-learning-with-verifiable-rewards rollout generation, i.e. to the model generating reasoning
traces for itself during training. Separately, experimentation, failed runs and ablations accounted for
82.2% of total compute, against the ~50% previously reported for pretraining-focused pipelines. Final
training runs alone came to 1.95 GWh; the full development process came to ~12.3 GWh, 4,251 tCO2eq and
15,887 kL of water.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| 32B Think post-training | 96,561 GPU-hr → 98,464 DC kWh → 32,690 kg CO2 → 127 kL water | Measured GPU power x 1.74 server/IT x 1.2 PUE |
| 32B Instruct post-training | 7,128 GPU-hr → 5,659 DC kWh → 1,878 kg CO2 → 7 kL | Same |
| Ratio Think : Instruct post-training energy | 17.4x | Same cluster, same base model |
| 7B Think vs Instruct post-training | 8,524 vs 4,646 DC kWh (1.8x) | Same |
| Share of Think post-training energy from RLVR rollouts | 87% | Per-stage measurement |
| Final training runs, all variants | 1,485,329 GPU-hr; 1,947,330 DC kWh; 646,512 kg CO2; 2,512 kL | Sum of table 2 rows |
| Total including development | ~12.3 GWh; 4,251 tCO2eq; 15,887 kL | Development = 82.2% of total compute |
| Development share of compute | 82.2% (vs ~50% in prior pretraining-focused work) | Cluster accounting |
| Datacenter overhead multiplier | 2.088x GPU power (1.74 server/IT x 1.2 PUE) | 1.74 from Epoch AI; PUE 1.2 self-reported for the cluster |
| Carbon intensity | 0.332 kg CO2/kWh | Austin Energy (Texas), cluster-specific |
| Water | WUE_onsite 0 L/kWh (closed loop), WUE_offsite 1.29 L/kWh | Water is entirely from power generation, not cooling |
| Embodied (amortised, 4-yr) | 0.013 kg CO2eq and 0.003 L per GPU-hour | Authors call these "rough approximations"; vendors disclose nothing |

## Methodology

Per-GPU power sampled at sub-second intervals on the actual training cluster (Cirrascale, Texas, NVIDIA
H100-80GB HGX nodes). Datacenter power is derived as P_GPU x 1.74 x PUE, where the 1.74 factor covers
non-GPU server and IT infrastructure — an improvement on the common practice of applying PUE to GPU power
alone, which understates by roughly 40%. Carbon is energy x grid carbon intensity; water is energy x
(WUE_onsite + WUE_offsite). Operational figures are measured-then-scaled; carbon, water and embodied
figures are estimated from published factors.

The 7B/32B Think-vs-Instruct comparison is unusually clean as an experiment: both variants branch from a
shared base model on the same hardware, so the 17x is a like-for-like difference attributable to the
post-training recipe rather than to model size, cluster or grid.

## Limitations and conflicts

Authors are at the organisation that built and released Olmo 3 (Ai2), so this is self-reported data about
their own models — but reported in the direction that makes their own costs look larger, which is the
opposite of the usual self-reporting bias. Carbon intensity is a grid annual average for one Texas
utility, not hourly marginal; using annual average understates variance and may over- or under-state
actual emissions substantially. Embodied impacts are acknowledged to be weak estimates. Inference energy
is out of scope entirely — the paper covers development only, so it says nothing about the lifetime cost
of serving these models.

The 17x figure is specific to Olmo 3's RLVR recipe at 32B. The 7B pair shows only 1.8x, so the multiplier
is not a stable constant and should not be transplanted to other labs' reasoning models.

## Relation to existing corpus

No direct overlap; the repo has no Olmo, no post-training, and no RL-rollout energy accounting. It
extends /research/ghg/017-wang-2023-bert-finetuning-energy-carbon.md (fine-tuning energy) by three orders
of magnitude and a generation of method. Strubell also appears as an author in
/research/frugal/027-luccioni-2024-power-hungry-processing.md.

The development-overhead finding (82.2%) is the strongest available rebuttal to per-model training-energy
figures quoted anywhere in the corpus: any figure for "the cost of training model X" that counts only the
final run is understating total compute by roughly a factor of five.

---
Retrieved: 2026-09-19
Search: arXiv all:"reasoning models" AND all:"energy", sortBy=submittedDate
