# The EU AI Act requires GPAI providers to document model energy consumption, but only to regulators and only for training

**Topic:** Policy and regulation — what AI-specific environmental disclosure is legally binding in the EU
**Source:** Regulation (EU) 2024/1689 (Artificial Intelligence Act), as amended by Regulation (EU) 2026/1744
**Type:** primary legal text
**URL:** https://eur-lex.europa.eu/eli/reg/2024/1689/oj
**Published:** 2024-07-12 (OJ L, 2024/1689); amended by https://eur-lex.europa.eu/eli/reg/2026/1744/oj (OJ 2026-07-24, in force 2026-07-27)

## Finding

The AI Act contains exactly one binding AI-specific energy disclosure obligation: Annex XI, Section 1, point 2(e) requires providers of general-purpose AI models to document the "known or estimated energy consumption of the model", with the fallback that "where the energy consumption of the model is unknown, the energy consumption may be based on information about computational resources used". The obligation runs through Article 53(1)(a), which requires the technical documentation to be drawn up, kept up to date, and provided to the AI Office or national competent authorities *on request*. There is no publication requirement, no threshold, no unit specified in the legal text, and no defined system boundary. Article 53(2) exempts free and open-source models with publicly available parameters from Article 53(1)(a) entirely, unless the model is designated as presenting systemic risk.

## Key Data

| Item | Value | Boundary / method |
|------|-------|-------------------|
| Legal hook for energy | Annex XI §1 point 2(e) | Applies to all GPAI providers, not only systemic-risk models |
| Adjacent compute item | Annex XI §1 point 2(d): FLOPs used for training, training time | Training only |
| Route of disclosure | Art. 53(1)(a) → AI Office / NCAs on request | Not published; Art. 78 confidentiality and trade-secret protection applies |
| GPAI obligations applicable from | 2 August 2025 (Art. 113) | Chapter V |
| Models on market before 2 Aug 2025 | Compliance required by 2 August 2027 (Art. 111(3)) | Transitional |
| Commission enforcement powers over GPAI from | 2 August 2026 | Requests for information, model access, fines |
| Methodology delegated act (Art. 53(5)) | Not adopted as of 2026-09 | Commission "may" adopt; discretionary |
| Open-source carve-out | Art. 53(2) | Removes the energy documentation duty for non-systemic-risk open-weight models |

## Methodology

Reading of the consolidated legal text. Dates taken from Article 113 and Article 111(3) of Regulation 2024/1689, and from Regulation (EU) 2026/1744 (the "Digital Omnibus on AI"), published in the Official Journal on 24 July 2026 and in force 27 July 2026. The Omnibus deferred stand-alone high-risk obligations under Annex III from 2 August 2026 to 2 December 2027 and product-embedded high-risk systems to August 2028; it did not defer or amend the Chapter V GPAI obligations or Annex XI point 2(e), which remain applicable from 2 August 2025.

## Limitations and conflicts

The statutory text fixes no unit, no reporting period, no accelerator-versus-facility boundary, and no treatment of PUE, embodied emissions, or inference. "Known or estimated" with an explicit compute-based fallback allows a provider to satisfy the obligation with a back-of-envelope FLOPs-to-joules conversion. Because disclosure is on request and protected as confidential under Article 78, nothing in this provision makes a single number publicly checkable. The open-source exemption removes a large share of released models from scope. Any claim that the AI Act "mandates AI energy transparency" is inaccurate as of September 2026: it mandates AI energy documentation held by regulators.

## Relation to existing corpus

Supersedes the framing in /Users/olivier/DEV/research-ai-energy/research/policy/_index.md that "no dedicated AI environmental regulations exist" and the claims in 001/009 (Capraro 2024) and 012 (Batool 2025) that environmental provisions are absent from AI governance frameworks. A provision exists; it is narrow and non-public. See also 016 (Model Documentation Form) and 017 (missing standards).

---
Retrieved: 2026-09-19
Search: EUR-Lex ELI reg/2024/1689; artificialintelligenceact.eu/annex/11 and /article/53; EUR-Lex ELI reg/2026/1744
