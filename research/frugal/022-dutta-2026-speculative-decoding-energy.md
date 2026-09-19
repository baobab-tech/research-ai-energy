# Speculative decoding saved 2.51x energy in the best case and cost 1.6x more in the worst; the sign depends on the dataset

**Topic:** Frugal AI — measured energy effect of a widely deployed inference optimisation
**Source:** Dutta, Koley, Poddar, Ghosh & Ganguly (IIT Kharagpur) with Misra, Podder & Balani (Accenture Labs), 2026
**Type:** preprint (EACL Findings 2026)
**URL:** https://arxiv.org/abs/2602.09113
**Published:** 2026-02-09

## Finding

Across four model families and three task types, speculative decoding's energy effect ranges from a 2.51x
saving (Vicuna-13B with EAGLE-3 on HumanEval) to a 0.63x "saving" — that is, a 1.6x *increase* — on
CNN/DailyMail with Llama-70B. Summarisation is where it reverses: long, low-entropy outputs give poor
draft acceptance, so the drafter's tokens are generated and discarded, and the verification passes are
paid for anyway. Trained-drafter methods (EAGLE-2/EAGLE-3) were consistently positive at 1.34–2.51x;
generic assistant-model methods (CoGA/DyGA) ranged 0.77–2.0x. Latency and energy do not move together:
the paper's contribution is measuring the second after a literature that reported only the first.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Best case | 2.51x total energy saving — Vicuna-13B + EAGLE-3, HumanEval | GPU energy, NVIDIA A5000 24GB |
| Worst case | 0.63x (i.e. 59% more energy) — Llama-70B, CNN/DailyMail | NVIDIA A6000 48GB |
| EAGLE-2 / EAGLE-3 range | 1.34–2.51x saving | Trained draft heads |
| CoGA / DyGA range | 0.77–2.0x | Generic assistant models |
| Vicuna-13B + CoGA on CNN/DM | 0.96x (no saving) | Summarisation |
| Qwen3-8B on CNN/DM | 0.67x total energy (increase) | Summarisation |
| Target/draft pairs | Vicuna 7B & 13B / 68M; Llama 8B & 70B / 1B; Flan-T5 L & XL / Base; Qwen3 4B & 8B / 0.6B | |
| Hardware | A5000 (24GB) primary; A6000 (48GB) for 70B; Intel Xeon Silver 4210R, 128GB RAM | Single node |
| Datasets | HumanEval (164), GSM8K (256), CNN/DailyMail (256) | Code, maths, summarisation |

## Methodology

Direct GPU energy measurement on fixed hardware across the cross-product of model family, model size,
speculative decoding strategy and dataset. The energy ratio reported is total energy of speculative
decoding divided by total energy of vanilla autoregressive decoding on the same target model — so >1 is a
saving and <1 is a penalty, and the accounting includes the drafter's own energy, which is the term that
prior latency-only work omits.

Boundary is GPU-only on workstation-class Ampere cards (A5000/A6000), not datacenter H100/B200 with
production serving. Sample sizes per dataset are small (164–256 prompts).

## Limitations and conflicts

Three co-authors are at Accenture Labs, a consultancy selling AI deployment services; this does not
obviously bias the result, which is mixed rather than promotional. The hardware is not representative of
production serving: A5000/A6000 are workstation cards, batch behaviour and memory bandwidth differ
substantially from H100/H200/B200 nodes, and the paper does not test speculative decoding under
continuous batching at high concurrency — the regime where it is actually deployed and where its benefit
is known to shrink, because spare compute for drafting is scarcer when the batch is already saturated.
The measured savings are therefore likely an upper bound for production.

The paper is described as a survey with experiments; it does not report accuracy deltas, though
speculative decoding is output-equivalent by construction when verification is exact.

## Relation to existing corpus

No direct overlap; first excerpt on speculative decoding in the corpus. Reinforces the pattern in
/research/frugal/021 (Delavande et al.) that a serving optimisation validated on latency can be
energy-neutral or energy-negative, and that the workload determines the sign.

---
Retrieved: 2026-09-19
Search: arXiv abs:"speculative decoding" AND abs:"energy", sortBy=submittedDate
