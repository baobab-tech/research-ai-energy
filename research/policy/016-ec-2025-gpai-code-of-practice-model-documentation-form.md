# The GPAI Code of Practice reduces inference energy to a FLOPs count and sends no energy figure to downstream users

**Topic:** Policy and regulation — how the AI Act's energy documentation duty is operationalised in practice
**Source:** European Commission / AI Office, General-Purpose AI Code of Practice, Transparency chapter — Model Documentation Form
**Type:** official guidance (voluntary code deemed adequate means of compliance)
**URL:** https://digital-strategy.ec.europa.eu/en/policies/contents-code-gpai
**Source note:** form text retrieved from mirror https://lawgitech.eu/wp-content/uploads/2025/08/template.pdf
**Published:** 2025-07-10

## Finding

The Model Documentation Form — the operative instrument by which signatories discharge Annex XI — asks for training energy in MWh to two significant figures, but converts the inference half of "energy consumption of the model" into a compute metric rather than an energy metric. The form's item is "Benchmarked amount of computation used for inference", reported in floating point operations, with a footnote stating that because inference energy "depends on more than just the model itself, the information required for this item is limited to relevant information depending only on the model, namely computational resources used for inference." Every energy and compute item is checked for the AI Office and national competent authorities and unchecked for downstream providers. None is published.

## Key Data

| Item in the form | What is required | Recipients (AIO / NCAs / downstream) |
|---|---|---|
| Amount of energy used for training | Measured or estimated MWh, ≥2 significant figures; "N/A" permitted if a compute or hardware provider withholds critical information | ☒ ☒ ☐ |
| Measurement methodology (training energy) | Free text, ~100 words, "in the absence of a delegated act adopted in accordance with Article 53(5)" | ☒ ☒ ☐ |
| Benchmarked computation used for inference | FLOPs, ≥2 significant figures (e.g. 5.1×10^17) — not energy | ☒ ☒ ☐ |
| Measurement methodology (inference) | Description of a task (e.g. "generating 100000 tokens") and hardware (e.g. "64 Nvidia A100s") | ☒ ☒ ☐ |
| Amount of computation used for training | FLOPs; order of magnitude to NCAs, ≥2 significant figures to AIO | ☐ ☒ / ☒ ☐ |
| Training time | Range (<1 month / 1–3 / 3–6 / >6) to NCAs; wall-clock days and hardware-days to AIO | ☐ ☒ / ☒ ☐ |
| Confidentiality | Information shared with the AIO and NCAs treated under Article 78 AI Act trade-secret protection | — |

## Methodology

Direct reading of the Model Documentation Form PDF (text extracted locally; the checkbox columns AIO/NCAs/DPs were read from the table layout). Publication date of the Code from the Commission's own page. The Code is voluntary; the Commission treats adherence as an adequate means of demonstrating compliance with Articles 53 and 55, and non-signatories must demonstrate compliance by other means.

## Limitations and conflicts

The form was drafted through a multi-stakeholder process in which the largest GPAI providers participated as prospective signatories; several declined to sign parts of it. Three design choices limit what the regime can ever produce: the "N/A" escape hatch when a compute provider withholds data, which is exactly the situation for any model trained on rented cloud capacity; the substitution of FLOPs for joules at inference, which forecloses aggregate operational-energy reporting for the phase that dominates lifetime consumption of a deployed model; and the absence of any boundary definition for the training figure (accelerator, node, or facility including PUE), which makes MWh values from different providers non-comparable. The form itself concedes the gap by conditioning its methodology questions on the absence of an Article 53(5) delegated act.

## Relation to existing corpus

Operationalises 015. Directly relevant to the boundary-definition problem flagged across the /ghg folder: even under a binding regime, per-model energy figures arriving at the AI Office will carry provider-chosen boundaries. No direct overlap with existing policy excerpts.

---
Retrieved: 2026-09-19
Search: Serper "\"Model Documentation Form\" GPAI Code of Practice \"energy consumption\""; EC digital-strategy contents-code-gpai
