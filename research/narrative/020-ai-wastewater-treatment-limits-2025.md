# Almost all AI applications in wastewater treatment are predictive studies at small scale; two full-scale operational digital twins are identified worldwide, one of them covering only the sewer network

**Topic:** narrative — deployment evidence behind AI-for-environment claims in a named sector
**Source:** Andrea G. Capodaglio and Arianna Callegari, Department of Civil Engineering and Architecture, University of Pavia, 2025
**Type:** peer-reviewed (narrative review)
**URL:** https://doi.org/10.3390/w17020170
**Published:** 2025-01

## Finding

A review of AI research in wastewater treatment by two process engineers finds that successful full-scale applications are limited and consist mostly of on- or offline operational support with little real-time control, and that almost all applications in the sector involve predictive studies, often at small scale or with limited data use. The review identifies only a few reported full-scale operational plant digital twins and names two: Eindhoven, which models the aeration and anoxic bioreactors and runs quasi-real-time simulations every two hours, and Gothenburg, which covers the sewer network and inlet pumping station rather than the treatment plant itself. The barriers the authors identify are operational and institutional rather than algorithmic: laborious instrumentation maintenance, absence of process expertise in the design of current software, instability of control loops, and insufficient incentives for resource efficiency. A 2018 survey of 90 Belgian plant operators that the review cites found only dissolved oxygen and pH sensors in wide use, at 96% and 69% of plants, despite established and reasonably priced alternatives, which locates part of the gap upstream of AI in the instrumentation the models would need.

## Key Data

| Metric | Value | Boundary / method |
|--------|-------|-------------------|
| Character of sector applications | "almost all" are predictive studies, often small scale or limited data | authors' qualitative assessment of the reviewed literature; no count or denominator reported |
| Full-scale operational WWTP digital twins identified | "only a few reported"; two named (Eindhoven, Gothenburg) | authors' survey; Gothenburg covers the sewer system and inlet pumping station, not the plant |
| Eindhoven digital twin simulation cadence | every 2 hours, quasi-real-time | as reported by the cited source |
| Belgian plant sensor penetration, 2018 | dissolved oxygen 96%, pH 69% of plants | survey of 90 wastewater treatment companies, cited from a 2020 publication |
| Sludge residuals share of plant energy and economic balance | about 50% of each | cited from third-party literature |
| Sludge residuals share of wastewater-related GHG | almost 40% | cited from third-party literature |
| Review scope | final treatment plant only | collection systems excluded by the authors as warranting a separate review |
| References | 123 | — |

Background figures the review reproduces from third parties, none measured here: data centres at 1-2% of global generated power, about 200 TWh/y, projected to 3-4% by 2030 on AI demand; a ChatGPT query at 2.9 Wh against 0.3 Wh for a Google search; AI applications projected at about a fifth of data-centre power demand by 2028; an average data centre using over 1,000 m3/d of drinking-quality water and larger ones up to 20,000 m3/d; just under 5,400 US data centres as of March 2024, with a water footprint the authors' cited sources equate to at least 16 million people.

## Methodology

A narrative review of the AI-in-wastewater literature, scoped to the treatment plant and excluding the collection network. No search string, database list, record counts, screening protocol or PRISMA flow is reported, and no count of reviewed studies is given, so the deployment claim is the assessment of two domain specialists reading their field rather than a coded classification with a denominator. The authors do not measure energy, emissions or water at any plant. Their evidence for the deployment gap is the composition of the studies they reviewed plus the named absence of full-scale digital-twin installations.

## Limitations and conflicts

The authors state that the research received no external funding and declare no conflicts of interest. Both are academic civil and environmental engineers at the University of Pavia; neither is affiliated with an AI vendor or a water utility.

The central claim carries no number. "Almost all" is not a counted share, and without a denominator the strength of the deployment gap cannot be compared against the coded review evidence elsewhere in this folder. The review is scoped to wastewater treatment plants and says nothing about water distribution, drinking-water treatment or the collection network, which the authors exclude as a larger separate literature. The data-centre energy and water figures the paper reproduces are secondary, drawn in part from a Goldman Sachs note and other grey sources, and carry no boundary of their own. Publication in January 2025 means the review's literature cut-off predates the LLM-for-control work that has since appeared.

## Relation to existing corpus

Reproduces in a second sector the result `narrative/025-neubauer-2026-llm-hvac-no-sustained-deployment.md` establishes with a denominator for HVAC, where 4 of 66 LLM studies reach pilot level and none reports sustained operational deployment. Both find the literature concentrated in research and pilots rather than running installations, which bears on `narrative/021-iea-2025-energy-and-ai-avoided-emissions-scenario.md`: the IEA's own text states there is no momentum that could ensure widespread adoption of the applications its 1,400 Mt scenario depends on, and this review is sector-level evidence of what that absence looks like.

---
Retrieved: 2026-09-19
Search: DOI 10.3390/w17020170; MDPI open-access PDF extracted locally
