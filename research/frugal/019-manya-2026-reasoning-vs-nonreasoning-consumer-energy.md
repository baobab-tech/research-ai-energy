# Reasoning modes estimated at 15–20x the per-query energy of non-reasoning modes for tasks where the non-reasoning answer was judged sufficient

**Topic:** Frugal AI — accuracy-per-joule of reasoning vs non-reasoning inference; demand-side abatement
**Source:** Manya, Thorpe, Zhang, Shirk, He, Hsu (UNC Chapel Hill, Data-Driven EnviroLab) & Vandenbergh (Vanderbilt Law), with Arboretica (Rotterdam), 2026
**Type:** preprint
**URL:** https://arxiv.org/abs/2608.12350
**Published:** 2026-07-02

## Finding

Across ten commercial models from five providers, the reasoning variant was estimated to draw about 20x
the energy of the non-reasoning variant on simple tasks and about 15x on complex ones, while the authors'
quality assessment found the non-reasoning output sufficient for the task categories tested. Prompt-level
interventions on top of non-reasoning models cut estimated energy further: asking for a minimal answer
saved 38–63%, a terse "caveman" prompt 40–47% (but *increased* energy 5% on knowledge tasks), and simply
appending an energy-efficiency instruction 4–35%. The headline framing — savings equal to the annual
electricity of 141,000 US households — is an extrapolation from these per-query deltas, not a measurement.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Reasoning vs non-reasoning energy, simple tasks | ~20x | Estimated from client-side time-to-last-token and token counts |
| Reasoning vs non-reasoning energy, complex tasks | ~15x | Same |
| Non-reasoning baseline, knowledge tasks | 0.16 Wh median | Estimated; GPU power equation x PUE |
| Non-reasoning baseline, creation/synthesis tasks | 0.68 Wh median | Same |
| "Minimal answer" prompt saving | 38–63% depending on task type | Non-reasoning models |
| "Caveman" terse prompt saving | 40–47%; +5% on knowledge tasks | Non-reasoning models |
| "Energy-efficient persona" instruction saving | 4–35% | The least intrusive intervention |
| Extrapolated aggregate saving (reasoning→non-reasoning) | ≥141,000 US household-years of electricity | Daily-usage assumption, stated by authors as uncertain |
| Extrapolated saving (persona prompt only) | up to 7,200 US household-years | Same |
| Models tested | 10, across OpenAI, Google, Anthropic, DeepSeek, xAI (reasoning + non-reasoning pairs) | Commercial APIs, black box |

## Methodology

Energy is **estimated, not measured**. The authors have no access to the serving hardware, so they record
client-side time to last token plus reported token usage, then apply the estimation method of Jegham et
al. (2025): a model-specific power equation derived from assumed GPU configuration, multiplied by an
assumed PUE. Every absolute Wh figure therefore inherits the uncertainty of an assumed hardware and
serving stack for closed commercial models whose actual deployment (batch size, quantisation, parallelism,
hardware generation) is undisclosed.

The *ratio* between reasoning and non-reasoning modes is more defensible than the absolute levels, since
the two variants of a given provider are assumed to run on comparable infrastructure, and the difference
is dominated by generated token count — which is directly observed.

Four consumer behaviours were tested as abatement levers: switching to a non-reasoning model, adding an
energy-efficiency persona, requesting a minimal answer, and a terse "caveman" prompt.

## Limitations and conflicts

The claim that non-reasoning models "provide sufficient quality" rests on the authors' own task set and
quality judgement, not a standard benchmark with an accuracy score, so the accuracy-per-joule trade-off
is asserted at the task-category level rather than quantified. Reasoning models exist because they raise
accuracy on hard problems; a study whose task set finds them unnecessary has, in effect, selected tasks
where they are unnecessary. That is a legitimate finding about typical consumer traffic but not a general
one about reasoning models.

Client-side timing conflates network latency and queueing with compute. Vandenbergh (Vanderbilt Law) works
on private environmental governance and behavioural abatement, which is the frame the paper adopts; no
industry funding is disclosed in the abstract. The household-equivalence figures depend on an assumed
global daily query volume and should be treated as illustrative.

## Relation to existing corpus

No direct overlap. Together with /research/frugal/017 (Oviedo et al.) it brackets the reasoning-energy
question from two directions: 017 models a ~13x rise from longer generations under production batching,
this paper estimates 15–20x from the client side on commercial APIs. The two are consistent in direction
and roughly in magnitude despite entirely different methods, which is the strongest thing that can be
said for either number.

---
Retrieved: 2026-09-19
Search: arXiv all:"reasoning models" AND all:"energy", sortBy=submittedDate
