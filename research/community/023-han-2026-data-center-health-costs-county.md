# Modelled US data-centre air-pollution health costs reach $20.9bn and 1,262 deaths in 2028 under high growth, with the worst county bearing ~7x the national per-household burden and ~200x the least-affected

**Topic:** Environmental justice — the geographic distribution of data-centre air pollution damage, and how much of it lands away from host communities
**Source:** Yuelin Han, Zhifeng Wu, Pengfei Li, Adam Wierman, Shaolei Ren (UC Riverside and Caltech), 2026
**Type:** preprint, accepted for publication in Communications of the ACM 2026
**URL:** https://arxiv.org/abs/2412.06288
**Source note:** v4, 8 June 2026
**Published:** 2026-06-08 (v4); accepted CACM 2026

## Finding

Running data-centre electricity consumption and on-site generator emissions through EPA's COBRA screening model, the authors estimate US data-centre air-pollution health costs of $6.67 billion in 2023 rising to $11.67-20.90 billion in 2028 depending on growth scenario, with 433 attributable deaths in 2023 and 705-1,262 in 2028. The national share is modest — 1.31 percent of all US stationary fuel-combustion health damage in 2023, 3.53 percent by 2028 — but the distribution is not. More than 90 percent of the burden comes from scope-2 emissions at the power plants supplying the electricity, not at the data centre, so the damage largely falls on communities that host neither the facility nor its tax base. County-level per-household health cost in the worst county is about seven times the national average and roughly 200 times the lowest county. County-level data-centre health burden correlates with existing fuel-combustion health burden at r = 0.842, meaning the damage concentrates where pollution burden is already high.

## Key Data

| Metric | Value (95% CI) | Boundary / method |
|--------|----------------|-------------------|
| 2023 total health cost | $6.67bn ($5.03-8.32bn) | Scope 1 + 2; 176.39 TWh data-centre electricity |
| 2023 attributable deaths | 433 (320-546) | Scope-1: 32; scope-2: 401 |
| 2028 low-growth total | $11.67bn ($8.91-14.44bn); 705 deaths (529-880) | 325 TWh |
| 2028 high-growth total | $20.90bn ($15.95-25.85bn); 1,262 deaths (947-1,576) | 580 TWh |
| 2028 high-growth morbidity | ~600,000 asthma symptom cases | |
| Share of US stationary fuel-combustion health cost | 1.31% (2023) → 3.53% (2028 high) | US fuel-combustion total modelled at $507.79bn in 2023 |
| Scope-2 share of impact | >90% | Emissions at generating plants, not at the data centre |
| Per-household cost, highest vs national average | ~7x | |
| Highest vs lowest county | ~200x | |
| Correlation, data-centre burden vs existing fuel-combustion burden | r = 0.842 | County level, per household |
| Correlation, data-centre burden vs grid emissions | r = 0.901 | e.g. West Virginia coal plants serving Virginia data centres |
| Virginia backup generators, reference case (10% of permitted emissions) | ~14,000 asthma symptom cases, 13-19 deaths/yr, $220-300m/yr | Permitted levels as of Dec 2024 |
| Virginia backup generators at full permitted emission | $2.2-3.0bn/yr | Hypothetical, e.g. prolonged regional grid outage |
| Top counties by per-household cost (VA generator scope-1) | Fairfax City VA $99.5; Falls Church VA $58.3; Montgomery MD $46.9; Frederick MD $44.1; Loudoun VA $29.6 | Loudoun hosts the densest data-centre cluster yet ranks 10th |

## Methodology

EPA's COBRA (Co-Benefits Risk Assessment) screening model, a reduced-form source-receptor tool, not a full chemical transport model. Data-centre electricity is mapped to grid emissions by region; on-site generator emissions are derived from permitted levels with a 10 percent utilisation assumption as the reference case. COBRA converts emission changes to county-level PM2.5 and ozone concentration changes and then to health outcomes via published concentration-response functions, monetised with standard value-of-statistical-life and morbidity valuations.

The authors are unusually explicit about what the numbers are not: COBRA's 2023 and 2028 baseline emissions come from EPA's Emissions Modeling Platform 2016v1 reflecting regulations as of May 2018, and the estimates "should not be interpreted as assigning responsibility for any specific individual health outcome, establishing site-specific impacts, or implying that data centers are a dominant contributor to national air-pollution-related health burdens."

## Limitations and conflicts

No industry funding disclosed; academic authors at UC Riverside and Caltech. Shaolei Ren's group has published repeatedly on data-centre water and carbon footprints and has a consistent position that these impacts are under-reported, which is a research programme rather than a conflict.

The baseline emissions inventory is eight years stale relative to the modelled years, and predates both the recent coal-retirement delays and the 2025-2026 federal rollbacks — both of which push the estimate down relative to reality. COBRA is a screening tool; it cannot resolve sub-county exposure, so the environmental-justice conclusion is limited to county resolution and cannot speak to neighbourhood-scale siting, which is where most siting disputes actually occur. The authors say so. The generator reference case rests on an assumed 10 percent of permitted emissions with no empirical runtime data behind it; the true figure is unknown because runtime is not reported.

The second half of the paper proposes a "health-informed computing" scheduling framework; that is an engineering proposal, not a finding, and should not be cited as evidence of anything.

## Relation to existing corpus

No direct overlap. /Users/olivier/DEV/research-ai-energy/research/water/019-li-2023-environmental-equity-regional-water.md covers the same research group's equity work on water; this is the air-quality and mortality counterpart and is four years newer. Supplies the quantitative environmental-justice evidence the community folder lacked.

---
Retrieved: 2026-09-19
Search: WebSearch "2026 study data center backup generators air pollution health costs mortality quantitative peer reviewed published" -> Environmental Protection Network report ref. 14 -> arXiv 2412.06288v4
