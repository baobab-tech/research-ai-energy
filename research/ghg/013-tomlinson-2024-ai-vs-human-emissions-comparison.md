# AI writing emits 130-1500x less CO2e per page than a human, against a baseline that charges the writer a pro-rata share of their entire annual lifestyle footprint

**Topic:** GHG emissions — AI-versus-human task comparisons and their counterfactual
**Source:** Bill Tomlinson, Rebecca W. Black, Donald J. Patterson, Andrew W. Torrance, 2024
**Type:** peer-reviewed
**URL:** https://doi.org/10.1038/s41598-024-54271-x
**Published:** 2024-02

## Finding

Four generative systems (ChatGPT, BLOOM, DALL-E 2, Midjourney) are reported as emitting 130-1500x less CO2e per page of text and 310-2900x less per image than human writers and illustrators doing the same task. The ratios rest on an asymmetric boundary. The AI side counts only the electricity of one query plus an amortised share of training. The human side takes a national per-capita annual carbon footprint, divides it by all 8,760 hours in the year, and multiplies by the hours spent on the task, so the writer is charged for food, housing, transport and everything else in proportion to time spent writing. No counterfactual is applied: the hours a writer does not spend writing still carry the same per-capita emissions, so the human figure is an attribution of existing emissions and not an emission avoided by using AI. The paper's own worked example illustrates the problem, since the minute a person spends typing a prompt carries 30 gCO2e on this method, roughly 15 times the AI query itself.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| ChatGPT, per page of text | 2.2 gCO2e | 0.382 g inference + 1.84 g amortised training; estimated |
| BLOOM, per page of text | 1.6 gCO2e | 1.47 g inference + 0.10 g amortised training; estimated |
| ChatGPT inference term | 0.382 gCO2e/query | 3.82 tCO2e/day ÷ 10M queries/day, taken from an informal online estimate |
| ChatGPT training term | 1.84 gCO2e/query | 552 tCO2e ÷ 300M queries, assuming full monthly retraining of GPT-3 |
| BLOOM inference term | 1.5 gCO2e/query | 340 kgCO2e ÷ 230,768 queries, measured deployment (Luccioni et al.) |
| Human writer, US | ~1,400 gCO2e per 250-word page | 15 tCO2e/yr per capita ÷ 8,760 h = 1.7 kg/h, × 0.83 h at 300 words/h |
| Human writer, India | ~180 gCO2e per page | 1.9 tCO2e/yr per capita, same pro-rating |
| Reported writing ratio | 130x (ChatGPT vs India) to 1,400x (BLOOM vs US) | Figure 1; the abstract and figure caption round the top of the range to 1,500x |
| Writing ratio implied by the paper's own per-page values | 82x to 875x | 1,400 ÷ 2.2, 1,400 ÷ 1.6, 180 ÷ 2.2, 180 ÷ 1.6 |
| Laptop used by the human writer | 27 gCO2e per page | 75 W × 0.8 h via the EPA equivalencies calculator |
| Desktop used by the human writer | 72 gCO2e per page | 200 W × 0.8 h |
| DALL-E 2, per image | 2.2 gCO2e | assumed equal to ChatGPT because both sit on GPT-3 |
| Midjourney, per image | 1.9 gCO2e | 50 petaops ÷ 1.25 petaops/s on an A100 at 400 W = 4.5 Wh; worst case from a CEO interview |
| Human illustrator, US | ~5,500 gCO2e per image | 1.7 kg/h × 3.2 h |
| Human illustrator, India | ~690 gCO2e per image | 0.22 kg/h × 3.2 h |
| Illustration ratio | 310x (DALL-E 2 vs India) to 2,900x (Midjourney vs US) | consistent with the stated per-image values |
| Illustrator time per image | 3.2 h | $200 average project fee ÷ $62.50/h average rate |
| Human writing speed | 300 words/h | Mark Twain's output, from a magazine article |
| GPT-3 training | 552 tCO2e, 1,287 MWh | Patterson et al.; secondary citation |
| BLOOM training | 50.5 tCO2e, 433 MWh | Luccioni et al.; secondary citation |
| Embodied A100 | 150 kgCO2e per GPU | amortised over a 1.5-year life gives 0.0001 g/query, 2-5 orders of magnitude below training and inference |
| Embodied inference server | ~2,500 kgCO2e | 0.03 g/query at 3.8 s per page |
| Human time writing the prompt | 30 gCO2e for 1.06 min | ~15x the AI query, by the paper's own method |

## Methodology

A four-stage life-cycle framing (goal and scope, inventory, impact assessment, interpretation) applied to published secondary figures rather than to new measurements. Nothing was metered for this study except a single timing of ChatGPT producing 292 words in 4.4 seconds. The AI inventory is training emissions divided by an assumed query volume, plus a per-query operational figure, plus embodied hardware, which the authors compute and then set aside as negligible. The human inventory is a national per-capita annual footprint pro-rated by task duration, with the writer's computer counted separately. The illustration comparison substitutes a price-derived duration for a measured one. Data and calculations are posted at https://doi.org/10.17605/OSF.IO/YHTMQ.

## Limitations and conflicts

Andrew Torrance declares ownership of NVIDIA stock; the other three authors declare none. No funding statement appears. The paper states it used ChatGPT to draft parts of itself and cites its own result to justify that.

The writing ratios do not follow from the paper's own inputs. Dividing the stated human per-page values (1,400 g US, 180 g India) by the stated AI per-page values (2.2 g ChatGPT, 1.6 g BLOOM) gives 82x, 113x, 636x and 875x. Figure 1, the abstract and the caption instead report 130x, 180x, 1,100x and 1,400x, each about 1.6 times larger, and the abstract raises the top of the range again to 1,500x. The illustration ratios are internally consistent; the writing ratios are not.

Three of the four AI inputs are weak. The ChatGPT operational figure of 0.382 g/query comes from an informal online estimate, not a measurement. The amortisation assumes GPT-3 is fully retrained every month at 10 million queries a day, an assumption that sets the training term at 84% of ChatGPT's total. The Midjourney figure is derived from a CEO's remark about petaops in an interview. Only the BLOOM per-query figure rests on measured deployment data.

The comparison assumes AI output substitutes for human output at equal quality and that the displaced human hours produce no emissions elsewhere. The authors acknowledge rebound effects, professional displacement, training-data legality and non-substitutable tasks as excluded, and note the analysis holds only at 2023 model sizes.

## Relation to existing corpus

The 0.382 gCO2e operational term used here for a ChatGPT query is about 2.5x the 0.15 gCO2e that the 0.31 Wh median per-query energy of `research/ghg/026-oviedo-2026-per-query-inference-energy.md` implies at 480 gCO2e/kWh, despite that later figure being full-node and PUE-inclusive while this one is an informal estimate. The remaining 1.84 g of the 2.2 g total is the assumed monthly-retraining term, not inference. The 150 kgCO2e embodied-GPU placeholder used here is the same figure `research/ghg/027-schneider-2025-tpu-lifecycle-embodied-emissions.md` identifies as 1.5-4x too low for measured AI accelerators, which does not change this paper's conclusion that embodied emissions are minor per query. Its per-task framing is the position `research/frugal/026-wright-2025-compute-energy-carbon-efficiency.md` argues against, on the ground that per-task gains do not constrain system-level totals.

---
Retrieved: 2026-09-19
Search: DOI 10.1038/s41598-024-54271-x; PDF from nature.com extracted locally
