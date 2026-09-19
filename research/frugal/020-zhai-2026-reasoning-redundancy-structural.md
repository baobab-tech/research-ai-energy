# 61–93% of reasoning steps in frontier chain-of-thought traces can be truncated without changing the answer, and the paper proves this is structural

**Topic:** Frugal AI — the limits of efficiency; why reasoning models overspend compute by construction
**Source:** Zhai, You & Wang (Fudan University), Yan (Chinese University of Hong Kong), 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2605.23926
**Published:** 2026-04-21

## Finding

Truncating the trailing steps of a correct chain-of-thought trace and forcing the model to answer
immediately leaves the answer correct for 61–93% of the trace across four frontier reasoning models and
two mathematical benchmarks; in six of the eight (model, benchmark) conditions the median critical prefix
is a single segmented step. The redundancy falls with problem difficulty but survives it — on MATH-500
Level-5 problems it is still 46–85%. The paper then proves that under any length-agnostic outcome reward,
no finite expected stopping time is optimal, so over-thinking follows from how reasoning models are
trained rather than from a defect in any particular model, RL algorithm, base model or data distribution.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Step-level redundancy, all conditions | 61–93% | 4 frontier reasoning models x 2 maths benchmarks |
| Median critical prefix | 1 segmented step, in 6 of 8 conditions | The trace can usually be cut to its first step |
| Redundancy on hardest problems (MATH-500 Level-5) | 46–85% | Difficulty reduces but does not remove it |
| Theoretical result | Under length-agnostic outcome rewards, no finite expected stopping time is optimal | Proof, not measurement |
| Code | https://github.com/zhiyuanZhai20/how-much-thinking-is-enough | Released |

## Methodology

Redundancy rho is defined operationally against the model itself: the largest fraction of trailing
segmented steps that can be removed from a correct trace while the same policy, forced to stop thinking
and emit an answer, still answers correctly. This is a per-trace, per-model measurement, not a comparison
against an external oracle, which removes the usual objection that a shorter trace merely reflects an
easier grader. Robustness to the choice of judge model family is checked.

The theoretical half is an argument about the reward structure: because the reward does not penalise
length, and there is always some non-zero probability that another step improves the answer, the optimal
policy never stops. The result is stated to hold whether the policy comes from RL or from distillation.

**No energy or power figures appear in this paper.** The cost is expressed in latency, GPU time and
tokens. Converting redundancy to joules requires a separate energy-per-token measurement (see
/research/frugal/021 or 025).

## Limitations and conflicts

Mathematical reasoning benchmarks only; whether the same redundancy holds for agentic, coding or
open-ended tasks is untested, and those are the workloads where token counts are highest in practice.
Truncation is applied to traces already known to be correct, so the measure says how much of a *successful*
trace was surplus, not what fraction of all generated tokens could be saved in deployment — a router
cannot know in advance which prefix suffices. The academic-affiliation authors declare no industry funding.

The practical implication is bounded by that last point: the measurement establishes headroom, not a
deployable saving.

## Relation to existing corpus

No direct overlap. This is the corpus's only source giving a mechanism for why reasoning inference is
expensive, and it cuts against the optimistic framing in /research/frugal/017 (Oviedo et al., Microsoft),
which treats test-time-scaling energy as a workload characteristic to be managed by routing and
efficiency. If over-thinking is structural in the reward design, the efficiency levers that
017 counts toward its 8–20x headroom are addressing a symptom.

---
Retrieved: 2026-09-19
Search: arXiv all:"reasoning models" AND all:"energy", sortBy=submittedDate
