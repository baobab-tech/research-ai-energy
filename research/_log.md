# Search Log

Records searches performed, results found, and excerpts created.
Negative results are recorded deliberately: they mark where evidence does not yet exist.

---

## 2026-09-19 — Eight-area refresh

First update since 2026-01-16. Scope widened beyond academic databases to agency reports,
grid-operator data, regulatory filings and corporate disclosures. Eight parallel searches.

---

### GHG research log — 2026-09-19

Area: greenhouse gas emissions, hard numbers. Files 022-032 written to research/ghg/.

## Duplicate checks run first
`grep -ril` across research/ for: IEA, Shehabi, LBNL, Berkeley Lab, EIA, Short-Term Energy Outlook,
guidi, "de vries", devries, digiconomist, hyperscale, eGRID, 2502.01671,
"life-cycle emissions of ai hardware", "compute carbon intensity", Ironwood, "test-time scaling",
"energy use of AI inference".
Result: IEA appeared only as a search-log line in research/_log.md. LBNL/Shehabi appeared only as a
citation inside two Lei 2025 excerpts, never as a source. EIA, de Vries-Gao, Guidi, Epoch, the TPU LCA
and the Joule inference paper appeared nowhere. No duplicates created.

## Searches that produced excerpts
1. WebSearch "origin of 80 million tonnes CO2e AI 2025 emissions New York City comparison"
   -> de Vries-Gao 2025, Patterns, DOI 10.1016/j.patter.2025.101430. Full text via PMC12827721. -> 022
2. WebFetch iea.org/reports/energy-and-ai/energy-demand-from-ai -> 023
3. WebSearch "IEA Energy and AI Observatory 2026 update" -> Key Questions on Energy and AI,
   published 2026-04-16; executive summary fetched -> 024
4. WebSearch "LBNL 2024 United States Data Center Energy Usage Report Shehabi"
   -> PDF downloaded, pdftotext extracted locally (WebFetch could not parse the 3.8 MB PDF) -> 025
5. WebSearch "2026 measured energy per token LLM inference Wh full-stack PUE production"
   -> Oviedo et al., Joule 2026; cell.com returned 403, used arXiv 2509.20241 PDF -> 026
6. WebSearch "semiconductor fab carbon footprint per wafer GPU manufacturing embodied emissions TSMC"
   -> led to Google TPU LCA arXiv 2502.01671, PDF extracted -> 027
7. WebSearch "Google 2026 Environmental Report Scope 1 2 3 FY2025"
   -> sustainability.google/files/google-2026-environmental-report PDF extracted -> 028
8. WebSearch "Microsoft 2026 Environmental Sustainability Report FY2025 Scope 3"
   -> Environmental Data Fact Sheet PDF extracted (Table 1A) -> 029
9. WebSearch surfaced arXiv 2606.05420 (Guidi et al., Harvard) -> PDF extracted -> 030
10. WebSearch "EIA Short-Term Energy Outlook September 2026 data centers"
    -> eia.gov Today in Energy 67704 (AEO2026) + press release 592 (Sep 2026 STEO) -> 031
11. WebSearch "2026 training compute carbon emissions frontier model tCO2e Epoch AI"
    -> epoch.ai grok-4-training-resources + Stanford AI Index 2026 via IEEE Spectrum -> 032

## Came up empty / not used
- TSMC and Samsung wafer-level CO2e per wafer: no primary disclosure at wafer granularity found.
  Secondary sources (TechInsights, imec, Devera) give industry aggregates (e.g. ~185 MtCO2e/yr for all
  integrated-circuit production) without a traceable method. Not written up — would have violated the
  no-abstract-only-speculation rule. Google's TPU LCA (027) is the only first-party accelerator
  manufacturing disclosure that exists.
- NVIDIA accelerator LCA: nothing equivalent to Google's TPU disclosure published.
- Meta and Amazon FY2025 environmental reports: not pursued after Google and Microsoft gave the same
  structural finding (market-based vs location-based gap). Remaining gap.
- AI-specific emissions from any operator: none disclosed by anyone. This is the binding constraint on
  the whole field, noted in 022, 023, 028 and 029.
- OpenAlex queries were not needed; the material gaps were all agency and corporate primary sources.

## Verdict requested on the README claim
Sourced, but misstated. See 022 and the note appended to research/ghg/_index.md.

## Remaining gaps
- Meta, Amazon, NVIDIA FY2025 disclosures.
- Wafer- or fab-level emission factors from a foundry primary source.
- Any operator disclosing AI workload emissions separately from total data-centre emissions.
- Consequential (marginal) emissions of added data-centre load; 030 is attributional only.

## Cross-folder overlap discovered late (parallel agents)
Three sources I captured were independently captured by agents working other folders, from different
angles. Cross-references added in both directions from my files:
- Oviedo et al. 2026 -> research/frugal/017 (efficiency pathways angle); my 026 records the per-query
  number and its boundary.
- Google 2026 Environmental Report -> research/washing/018 and /019 (disclosure-practice angle);
  my 028 is the emissions-inventory reading.
- Microsoft 2026 report -> research/washing/017 (REC withdrawal); my 029 is the inventory reading.
- LBNL: research/datacenters/016 captures the June 2026 LBNL *2025 Update* (LBNL-2001758), which revises
  2024 down to 192 TWh and projects 649 TWh in 2030. My 025 is the foundational 2024 report the brief
  asked for and remains the source of the 176 TWh (2023) historical figure. Cross-reference added.

---

### Water research log — 2026-09-19

Area: water consumption, hard numbers and contested estimates. Files 027-035 in research/water/.

## Searches run

### Productive
| Query / route | Tool | Result |
|---|---|---|
| Ceres "Water Behind the Watts" (named in brief) | WebFetch + curl PDF + pdftotext | → 028. PDF at ceres.org/download/6489292d-... |
| "2026 paper replication critique Google Gemini per-prompt water energy estimate excludes water embedded in electricity generation" | WebSearch | → Sharma et al. 2026, DOI 10.3390/green1020008 → 027. **The key hit.** |
| DOI 10.3390/green1020008 full text | www.mdpi.com 403; mdpi-res.com/d_attachment/green/green-01-00008/article_deploy/green-01-00008.pdf works | full 25-page text |
| "LBNL 2024 US Data Center Energy Usage Report water" | WebSearch → eta-publications.lbl.gov PDF | → 029. escholarship.org PDF link returns HTML; eta-publications works |
| "Microsoft 2026 environmental sustainability report FY2025 water" | WebSearch → cdn-dynmedia-1.microsoft.com both PDFs | → 030. Table 15 site-level is new in this report |
| "Google 2026 Environmental Report water" | WebSearch → sustainability.google/reports/... → PDF path from page | → 031. 98-page PDF |
| "2026 study data center siting water stressed basins groundwater aquifer" | WebSearch | → arXiv 2607.02531 (Guidi & Dominici) → 032; arXiv 2606.21760 (Akinade et al.) → 033 |
| "AGU Advances 2026 data center water use fraction national" | WebSearch | → CRS R49057 → 034; ITIF Gaster → 035 |
| CRS R49057 | crsreports.congress.gov 403; congress.gov/crs_external_products/R/PDF/R49057/R49057.1.pdf works | full text |
| ITIF report | curl page + HTML strip | full report is on the page, not a separate PDF |

### Empty or blocked
| Query / route | Outcome |
|---|---|
| OpenAlex `search=` free-text, 2026 filter, several phrasings | Useless. Returns nanoparticle synthesis, MXene films, apricot production. OpenAlex full-text relevance ranking is not usable for this topic. |
| OpenAlex `filter=title_and_abstract.search:` for "data center water", "water usage effectiveness" | Better but dominated by Zenodo duplicate grey literature. Two plausible hits not pursued: Maynooth "How we all pay for Big Tech: costs of data centres in Ireland" (doi 10.48460/mu.mural.00021841), "What Georgia Is Spending, What Georgia Is Getting: A Statewide Data Center Report" (Zenodo). |
| arXiv API `abs:"water" AND abs:"data center"` | Returned nothing — the query form failed silently. arXiv papers were found via WebSearch instead. |
| arXiv API `id_list=2508.15734` (Elsworth/Google) | Returned nothing; not needed, the 2026 Google report reprints the figure with its footnote. |
| Privette, Barros & Cai, *AGU Advances* 2026, doi 10.1029/2025AV002140 | **Blocked.** agupubs.onlinelibrary.wiley.com returns 403 on /doi/, /doi/full/, /doi/pdfdirect/, /doi/epdf/ with and without browser UA. Semantic Scholar returns abstract only; OpenAlex reports no repository full text. Gold OA, CC-BY-NC-ND, and still unreachable. Not written up — abstract-only would violate the brief. **Worth a manual retrieval.** |
| Meta FY2025 water disclosure | Not found. Latest is the 2025 Sustainability Report with 2024 data (1.6 billion gallons restored; targets 200% restoration in high-stress and 100% in medium-stress watersheds — the strictest watershed-matching rule of the three hyperscalers). datacenters.atmeta.com has an April 2026 blog post but no 2026 report with FY2025 figures. |
| "2026 assessment of water positive pledge progress" (several phrasings) | Nothing independent. All results are corporate self-reports or trade press restating them. Genuine gap. |
| "2026 direct-to-chip liquid cooling water energy tradeoff" | Almost entirely vendor blogs (Schneider, Introl, Alliance Chemical, Adam Silva Consulting, HydropureWater). Excluded per brief rule 4 on source quality. ITIF and CRS were used instead. |

## Retrieval notes worth reusing
- `pdftotext -layout` handles all of these cleanly. Ceres, LBNL, Microsoft, Google, CRS and both arXiv PDFs all extracted fully.
- MDPI: `www.mdpi.com` 403s everything including with a browser UA; `mdpi-res.com/d_attachment/<journal>/<journal>-<vol>-<art>/article_deploy/<file>.pdf` is open.
- CRS: `crsreports.congress.gov` 403s; `congress.gov/crs_external_products/R/PDF/<id>/<id>.1.pdf` is open.
- Wiley (AGU): no route found.
- HEAD requests 403 on doi.org/MDPI and congress.gov even where GET succeeds — don't use `curl -I` to validate these.

## Arithmetic done here, not in the sources
- Microsoft per-site withdrawal intensity (L/kWh) computed from Table 15 electricity and withdrawal columns. Fleet total 15.91 TWh / 4,717 ML = 0.296 L/kWh, consistent with Microsoft's reported 0.27 L/kWh WUE. Site range 0.014 (Dublin) to 1.028 (Phoenix), ~70x. Sum of disclosed site replenishment = 6,247 ML of the 14,200 ML global total, so >half the replenishment is at locations not in the datacenter table.
- Google replenishment as share of *total* consumption: 7,717 / 10,869 = 71% (against the 78% Google reports on a freshwater-only denominator).
- Unit conversions for the index comparison table (gal/kWh ↔ L/kWh, Mgal ↔ ML ↔ m3).

## Duplicate check
`grep -ril` across research/ for: mistral, ceres, hidden thirst, water cost of intelligence, shehabi, drained by data, elsworth. Only hits were the existing 017, 022, _index.md, _log.md and datacenters/012. No source written up here was already in the tree.

---

### Search log — data-centre infrastructure (files 016-025)
Date: 2026-09-19

## Queries run
**Serper /search**
- "data center interconnection queue 2026 GW large load ERCOT" → ERCOT Senate deck (used, 017), ERCOT April 2026 hearing deck, ercotqueue.com, Utility Dive 438 GW story
- "PJM 2026 data center load forecast GW interconnection" → PJM 2026 Load Forecast Report PDF (used, 022); Utility Dive "PJM trims near-term forecast on stricter DC screening" (noted, not captured — gap)
- "LBNL 2024 United States Data Center Energy Usage Report PUE" → LBNL 2025 Update PDF (used, 016)
- "Verrus Beyond PUE 2026..." → verrusdata.com/news/beyond-pue (used, 023); DCD opinion piece 403
- "Crane Clean Energy Center Three Mile Island restart 2026..." → ANS, Utility Dive, DOE EDF (used in 020)
- "Palisades nuclear plant restart 2025 2026 Holtec..." → ANS 2026-07-08 no-restart-date piece (used, 020)
- "small modular reactor data center PPA 2026 in service date none operating" → Carnegie (used, 020); Bulletin of the Atomic Scientists 2026-07 (not captured — candidate)
- "xAI Memphis gas turbines permit Title V emissions 2026 Shelby County" + "SELC xAI Memphis turbines Clean Air Act appeal 2026" → Earthjustice/SELC/techpolicy.press (used, 025)
- "data center flexible load curtailment 2026 study Norris Duke Nicholas Institute" → LBNL Granderson et al. (used, 021); Duke Nicholas "Rethinking Load Growth" (not captured — 2025, likely already the Norris et al. 2025 cited inside 021)
- "IEA Energy and AI Observatory 2026 ... by country" → IEA Energy and AI (used, 018)
- "EirGrid Ireland data centre electricity 2026 CRU moratorium" → led to CSO (used, 019)
- "AI accelerator depreciation schedule 2026 hyperscaler useful life GPU six years overbuild" → only commentary/substack, no primary filing (EMPTY — see gaps)
- "data center vacancy cancelled leases 2026 ... CBRE absorption" → CBRE H1 2026 (used, 024)

**WebSearch**
- "US 40% of world data center electricity 2026 dataset IEA Ember"
- "CSO Ireland data centres metered electricity consumption 2025 2026"

## Technique note
WebFetch returns raw binary for PDFs and cannot parse them. Every PDF here was downloaded by WebFetch to the tool-results cache, then text-extracted locally with `pdftotext -layout`. Without that step the ERCOT, LBNL, PJM and LBNL-flexibility sources would all have been unusable.

## Came up empty / blocked
- **Forbes article (the 40% claim itself)**: HTTP 403 to automated retrieval. Verified the claim against the underlying datasets instead (018) rather than citing the article's framing.
- **Reuters xAI piece, SELC page, NRC reactor record, epw.senate.gov letter, escholarship, CBRE**: all 403 to plain curl; CBRE, SELC and escholarship content was obtainable via WebFetch or is mirrored, NRC and the Senate letter were not read at all and are flagged as such in 020 and 025.
- **xAI permits themselves**: Shelby County Health Department permit numbers and conditions are not published in machine-readable form. 025 rests entirely on litigant characterisations and says so.
- **Accelerator depreciation**: no primary filing found. Only secondary commentary (CNBC, substacks, Burry posts). Would need 10-K/10-Q property-and-equipment notes read directly.
- **Nordics**: no 2026 grid-operator or agency source located (Svenska kraftnät / Statnett / Fingrid not searched thoroughly).
- **Georgia**: Georgia Power IRP not searched.
- **24/7 CFE progress**: no 2026 hourly-matching progress report found. Google's own 24/7 CFE report and the UN 24/7 Carbon-Free Energy Compact were not located in a 2026 edition. The unbundled-REC-vs-hourly-matching question is therefore addressed only obliquely, via the Meta/Clinton credits structure in 020.

## Remaining gaps for a follow-up pass
1. Energised-capacity data. Every source here reports requests, forecasts or leases. Nobody publishes GW actually energised by year. This is the single biggest hole.
2. Utility 10-K / rate-case filings quantifying data-centre revenue and cost allocation to other ratepayers.
3. Hourly carbon-free energy: Google/Microsoft 2026 CFE percentages by region, and any independent audit of them.
4. Accelerator depreciation from primary filings.
5. Georgia Power IRP, Dominion Virginia IRP, and Nordic TSO data-centre load figures.
6. Whether any hyperscaler has signed a mandatory-curtailment tariff (021 shows the tariffs exist; no evidence found that AI campuses take them).

## Cross-folder overlaps found at write-time (parallel agents)
Three files appeared in other folders during this session and were reconciled rather than duplicated:
- `ghg/025-shehabi-2024-lbnl-us-data-center-energy.md` is the **2024** LBNL report. My `datacenters/016` is its official 2026 successor and supersedes it on every overlapping number (2023: 176 TWh → 2024: 192 TWh with history revised down; 2028 range 325-580 TWh → 464 TWh point). Noted in both directions in 016.
- `ghg/023-iea-2025-energy-and-ai-datacentre-electricity.md` captures the same IEA source as my `datacenters/018`. Kept 018 for the materially different finding (the US-share arithmetic, which needs a second dataset and which neither file states alone) and pointed all IEA-baseline claims at the ghg file.
- `community/022-naacp-xai-2026-memphis-turbines-clean-air-act.md` cites the actual court filings (N.D. Miss. 3:26-cv-00074) and gives 2,508 t/yr NOx across 33 turbines — better sourced than my `datacenters/025`, whose figures come from NGO case pages and are an earlier snapshot. 025 explicitly defers all emissions claims to community/022 and is retained only for the infrastructure angle (~1.2 GW on-site gas, the 35→15 turbine permitting sequence, 300 MW grid vs 1,200 MW on-site, DOJ intervention).

---

### Community folder research log — 2026-09-19

Area: grid impact, electricity prices, ratepayers, community/siting conflict.
Files created: research/community/016 through 027 (12 excerpts). Existing 001-015 untouched.

## Searches run

| Query | Tool | Outcome |
|---|---|---|
| PJM capacity auction 2026 results data center load electricity price increase ratepayers | WebSearch | Led to Utility Dive -> Monitoring Analytics IMM report (primary) -> file 016 |
| PJM 2028/2029 Base Residual Auction results 2026 clearing price data center | WebSearch | PJM auction results PDF (primary) -> file 017 |
| "data centers" electricity bills econometric study 2026 retail rates causal estimate counties peer reviewed | WebSearch | arXiv 2606.19777 (EPRI) -> file 018; also surfaced E3 May 2026 report (PDF extraction failed, not used) |
| 2026 state public utility commission order large load tariff data center minimum take contract stranded cost | WebSearch | PA PUC press releases, Oregon PUC order 26-154, CoBank/DELTa -> files 019, 020 |
| Pennsylvania PUC M-2025-3054271 large load final order PDF | WebSearch | Located docket; retrieved EAP Petition for Reconsideration (puc.pa.gov/pcdocs/1932400.pdf) -> file 019 |
| SEPA NCCETC DELTa Database Emerging Large-Load Tariffs 2026 report | WebSearch | DSIRE Insight Sep 2026 analysis -> file 020 |
| data center project cancellations quadrupled 2025 opposition moratorium count Data Center Watch | WebSearch | Traced claim to Baird note via Utility Dive -> file 021 |
| Data Center Watch report 2026 "$64 billion" blocked delayed 10a Labs methodology | WebSearch | Base report PDF + Q1 2026 page + NBC News -> file 021 |
| xAI Memphis gas turbines permit 2026 NAACP lawsuit Shelby County air quality environmental justice Boxtown | WebSearch | SELC + Earthjustice press releases, case 3:26-cv-00074 -> file 022 |
| peer-reviewed 2026 study data center siting environmental justice income race pollution burden US census | WebSearch | WRI Feb 2026 insight; EDGI (403) ; led onward |
| 2026 study data center backup generators air pollution health costs mortality quantitative peer reviewed | WebSearch | EPN "Hidden Health Costs" report -> its ref 14 -> arXiv 2412.06288v4 (Han et al., CACM accepted) -> file 023; ref 13 -> EIP -> file 024 |
| Environmental Integrity Project "The Power Behind AI" gas power plants data centers 2026 | WebSearch | -> file 024 |
| 2026 coal plant retirement delayed data center load growth utility named plant postponed retirement date | WebSearch | EIA Today in Energy x2 -> file 025 |
| 2026 utility IRP filing cites data center load delay coal retirement | WebSearch | RMI State of Utility Planning 2026 H1; Latitude Media on Evergy -> file 025 |
| 2026 municipality water utility restricted denied data center water supply agreement renegotiated drought moratorium | WebSearch | CRS R49057 -> file 026 |
| 2026 study data center proximity home property values decline hedonic noise measured decibels | WebSearch | GMU CRA and Integra Realty Resources analyses -> file 027 |

## Dead ends / came up empty

- **E3, "Understanding the Drivers of Rising Electricity Rates and the Role of Data Centers"** (May 2026, ethree.com). PDF text extraction failed twice; did not write it up rather than speculate. Worth a manual read — it is likely the utility-side rate-decomposition counterpart to file 018.
- **Environmental Data and Governance Initiative** (July 2026) analysis of air pollution near EPA-regulated data centers: envirodatagov.org returns HTTP 403. Promising quantitative EJ source, unretrieved.
- **SEPA DELTa database landing page**: HTTP 403 to automated requests. Used the two published analyses of the database instead; noted in file 020.
- **Oregon PUC Order 26-154** (UM 2377, PGE large-load tariff, 7 May 2026): PDF exceeds the fetch size limit. Would be the second strong state order after Pennsylvania.
- **Baird research note** (Justin Hauke) behind the "cancellations quadrupled" claim: not public, no title, no date, no methodology in any secondary coverage. Flagged as unverified in file 021.
- **MIT CEEPR WP 2026-06** turned out to be about airplane noise, not data centres. Discarded as off-topic.
- **Frontiers in Climate 2026 Virginia health paper** (Gour, Ortiz, Maibach, 10.3389/fclim.2026.1648912): self-described exploratory literature review with no quantified health outcomes. Its $14-33/month bill and 267% wholesale price figures are second-hand. Not written up; superseded by Han et al. (file 023).
- **Frontier Group / Environment America "Energy Transition at Risk"**: 403 on fetch. Used EIA and RMI primaries instead.
- Searched for a peer-reviewed quantitative study of data-centre siting against race/income at census-tract level; the recurring "nearly half of ~700 data centers in above-median EJI tracts" figure is cited by WRI without naming the underlying study. Not written up.

## Judgement calls

1. **Files 016 and 018 directly contradict each other** and both are included deliberately. The contradiction is the finding: PJM's monitor measures the capacity component under binding scarcity in 2025-2027; EPRI measures all-in average retail rates nationally through 2024 when capacity was slack. Each file cross-references the other and states the reconciling condition.
2. **Conflicts flagged in every file**: EPRI (utility-funded) in 018; Monitoring Analytics' own policy position in 016; PJM's institutional interest in 017; EAP as an adversarial filer in 019; 10a Labs as an AI-industry vendor in 021; EIP and RMI as advocacy organisations in 024 and 025; developer commissioning in 027.
3. **Potential-to-emit is never reported as measured emissions** (files 022, 024). Flagged explicitly in both.
4. **The RESEARCH_PLAN's "cancellations quadrupled in 2025" line (line 22) should be amended or dropped.** It rests on a paywalled sell-side equity note with no stated method.

---

### Policy & regulation research log — 2026-09-19

Area: AI / data-centre environmental regulation. Files 015-025 created in /research/policy/.

## Duplicate checks run first
- `grep -ril "AI Act" research/` → only 001, 009 (generic policy comparison), _log.md
- `grep -ril "Energy Efficiency Directive\|1791" research/` → only _log.md
- `grep -ril "SB 253\|SB253\|SB 6\|FERC" research/` → nothing
No overlap with existing 001-014, which are ESG/CSRD/carbon-pricing academic work.

## Searches that produced excerpts
| Query | Tool | Outcome |
|---|---|---|
| AI Act Annex XI / Art 40 / Art 53 text | WebFetch artificialintelligenceact.eu + EUR-Lex ELI | 015, 017 |
| "Model Documentation Form" GPAI "energy consumption" | Serper → PDF, pdftotext | 016 (the strongest single find) |
| CEN-CENELEC JTC 21 standards delay / digital omnibus | WebSearch → bundesnetzagentur.de | 017 |
| Targeted consultation measuring energy consumption AI | WebFetch EC digital-strategy | 018 |
| EED Art 12 delegated regulation 2024/1364 | WebFetch EUR-Lex OJ | 019 |
| European database data centres first reporting round | WebSearch → op.europa.eu PDF, pdftotext | 020 |
| Texas SB 6 large load ERCOT | WebSearch + capitol.texas.gov + gtlaw | 021 |
| FERC large load co-location 2026 | WebSearch + bracewell.com | 022 |
| SEC rescind climate rule 2026; CA SB 253/261 | WebSearch + federalregister.gov API | 023 |
| 2026 state data centre legislation water/ratepayer | WebFetch multistate.us x2, afslaw.com | 024 |
| CRU Ireland data centre connection policy | WebFetch cru.ie | 025 |

## Retrieval failures (sources named but not read directly)
- ferc.gov — HTTP 403 to both WebFetch and curl on every path tried (/rm26-4, news releases). Federal Register API has no RM26-4 or show-cause document. Used Bracewell client alert as the retrievable source; docket numbers cross-checked against a second firm's summary. **Gap: the six show cause orders (195 FERC ¶ 61,211-61,216) have not been read in the original.**
- sec.gov — 403 to curl; substituted federalregister.gov/documents/2026/06/03/2026-11091 (200).
- lis.virginia.gov — React SPA, no server-rendered bill text; legacylis 404s for the 2026 session; legiscan 403. **Gap: Virginia HB 1393 / HB 496 / SB 553 enrolled text and chapter numbers unverified.**
- virginiamercury.com, whitecase.com, akingump.com, gtlaw.com (second attempt) — 403.
- EUR-Lex HTML for the full AI Act truncates in the recitals; article text taken from artificialintelligenceact.eu, EUR-Lex ELI cited as the authority.
- Official EC copy of the Model Documentation Form is a DOCX behind digital-strategy.ec.europa.eu/en/policies/contents-code-gpai; the text was read from a mirrored PDF (lawgitech.eu). Content matches the Commission's description.

## Searched, nothing worth writing up
- Amsterdam/Haarlemmermeer, Singapore and Chile moratoria: only tertiary aggregator pages (electricchoice.com, ailawsbystate.com) with no linkable instrument. Singapore's 2019-2022 moratorium and its 2024 Green Data Centre Roadmap replacement were not confirmed against IMDA/EMA primary sources. **Open gap.**
- EPA permitting for on-site data-centre generation: nothing specific surfaced beyond Virginia DEQ's Tier 4 generator rule (effective 1 July 2026), which I did not verify against the Virginia Register.
- US federal executive action on AI infrastructure in 2026 beyond the Secretary of Energy's 23 Oct 2025 directive to FERC: not pursued to a primary source.
- Ohio: executive pause on tax-credit exemptions (27 May 2026) is not a statute; noted in 024's table, not given its own excerpt.
- Georgia SB 476 (tax credit repeal) passed the Senate 12 Feb 2026; final disposition not established.

## Open gaps for a follow-up pass
1. FERC show cause order text and the RTO compliance filings due 17 Aug 2026 — what the RTOs actually proposed.
2. Whether the Ninth Circuit ruled on SB 253/261 after January 2026, and whether the 10 Aug 2026 SB 253 filings happened.
3. Second EU reporting round (returns due 15 May 2026, covering 2025) — was coverage above 36%? No published assessment found.
4. Virginia enrolled bill text and chapter numbers.
5. Non-EU/US moratoria (Singapore, Netherlands, Chile) against primary instruments.
6. Whether any GPAI provider's Annex XI energy figure has become public through any route.

---

### Search log — Greenwashing (evidence, not theory) — 2026-09-19

Area: documented, quantified discrepancies between AI/cloud company environmental claims and underlying data.
Folder: research/washing/ — files 017-026 created. Existing 001-016 untouched.

## Primary documents retrieved and text-extracted

| Document | URL | Status |
|---|---|---|
| Microsoft 2026 Environmental Data Fact Sheet (FY2025) | https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/msc/documents/presentations/CSR/2026-Microsoft-Environmental-Data-Fact-Sheet-PDF.pdf | full text via pdftotext; complete FY20-FY25 scope tables |
| Google 2026 Environmental Report | https://sustainability.google/files/google-2026-environmental-report.pdf | full text (8,088 lines); data tables, methodology, endnotes |
| Meta 2025 Environmental Data Index | https://sustainability.atmeta.com/wp-content/uploads/2025/10/Meta_2025-Environmental-Data-Index.pdf | full text; market vs location-based table 2020-2024 |
| Amazon 2025 Sustainability Report | https://sustainability.aboutamazon.com/2025-amazon-sustainability-report.pdf | full text; 2019-2025 scope series, water sections |
| Amazon Carbon Methodology (July 2026) | https://sustainability.aboutamazon.com/carbon-methodology.pdf | full text; confirms market-based-only, EACs on Scope 1/3 |
| WattTime Meta emissions accounting case study | https://watttime.org/wp-content/uploads/2025/06/WattTime-Meta-Emissions-Accounting-Case-Study-vFinal-202505b.pdf | full text; three-methodology comparison |
| Bjørn, Lund & Brander, ERL 20(2) | https://iopscience.iop.org/article/10.1088/1748-9326/ada45a | fetched via WebFetch |
| InfluenceMap, GHGP Scope 2 consultation | https://influencemap.org/insight/Corporate-Engagement-on-the-GHG-Protocol-Scope-2-Consultation-39494 | fetched 2026-08-28 publication |
| PracticalESG, 66-signatory letter | https://practicalesg.com/2026/04/66-signatories-send-letter-opposing-ghg-protocol-scope-2-changes/ | fetched |

## Searches run

- WebSearch "Google 2026 Environmental Report location-based emissions market-based Scope 2 2025" — hit, led to full PDF
- WebSearch "Microsoft 2026 Environmental Sustainability Report Scope 2 market-based location-based emissions FY2025" — hit, surfaced the unbundled REC discontinuation
- WebSearch "Meta 2026 sustainability report Scope 2 market-based location-based emissions 2025 data centers" — partial; Meta's latest published index is the 2025 one covering FY2024
- WebSearch "Meta sustainability report 2026 net zero scope 3 emissions 2025 renewable energy certificates" — led to WattTime case study
- WebSearch "Meta 'environmental data index' 2025 scope 2 location-based market-based metric tons" — located the primary PDF
- WebSearch "Amazon sustainability report 2025 carbon footprint scope 2 market-based location-based renewable energy matched 100%" — hit
- WebSearch "'Amazon' 2025 sustainability report scope 2 'location-based' tonnes CO2e emissions table 2025" — confirmed no location-based series is published
- WebSearch "2026 study market-based scope 2 accounting overstates emissions reductions hourly matching additionality RECs peer-reviewed" — surfaced Bjørn et al. and the June 2026 academic letter to GHGP
- WebSearch "GHG Protocol Scope 2 market-based method 2026 decision draft standard hyperscalers opposition Google Microsoft Amazon" — surfaced InfluenceMap and the 66-signatory letter
- WebSearch "2026 greenwashing complaint data center technology company environmental claims regulator advertising authority" — see gaps below

## Came up empty

- **No 2026 regulatory or advertising-standards action against a named technology company over AI/data-centre environmental claims.** Searches returned general greenwashing enforcement statistics (400+ actions globally in 2026, CMA Jan 2026 supply-chain guidance, ASA Active Ad Monitoring) but nothing sector-specific to cloud or AI. Either none exists or it is not indexed. This remains an open gap.
- **No 2026 assessment of the specific carbon credit types retired by hyperscalers.** Microsoft reports contributing to 45+ Mt of carbon removal across 29 projects and 10 pathways in FY2025, but no independent 2026 quality assessment of those specific retirements was found. The folder's Trencher 2024 file remains the only offset-quality source.
- **Meta's FY2025 data.** Meta's most recent published Environmental Data Index covers calendar 2024. No 2026 Meta report was located, so file 020 reports 2024 figures and says so.
- **Amazon location-based Scope 2.** Confirmed absent from both the report and the methodology document, not merely missed.
- Computing.co.uk "Meta's sustainability surprise" returned HTTP 403; its claims were independently verified against Meta's own data index instead.

## Notes on method

- Every figure in files 017-023 and 026 is read from the company's own PDF, not from press coverage. Secondary sources were used only to locate documents.
- Where a company's stated justification exists it is quoted in the Limitations section, per brief.
- File 025 (Bjørn et al.) is January 2025, outside the primary window. Included because the task prompt named these authors and the folder had no quantitative Scope 2 literature at all.
- File 021 (WattTime, May 2025) likewise predates the window; it is the only consequential emissions estimate for a named hyperscaler that was locatable.

---

### Frugal / efficient AI — search log, 2026-09-19

Area: measured efficiency, and the limits of efficiency. Folder /research/frugal/, files 017-026.

## Searches run

### arXiv (export API)
- `all:"reasoning models" AND all:"energy"`, submittedDate desc, 30 results
  → hits: 2605.01158 (Olmo 3 / Strubell), 2608.12350 (Manya), 2601.00823 (energy-aware routing to LRMs),
    2605.23926 (redundancy), 2603.00068 (env AI regulation — policy folder's territory), 2609.05512
    (reasoning-aware compression)
- `all:"tokens per joule" OR all:"energy per token"`, 30 results
  → 2608.28667 GreenBench (Apple Silicon), 2608.01891 (disaggregated attention-FFN), 2608.11226 (RL power
    control of training, Curcio), 2605.11733 (position: energy-to-token), 2603.20224 (Wilhelm/Kao,
    energy-per-token for test-time compute), 2609.11940 (edge battery), 2606.21428 (MoE edge)
- `abs:"quantization" AND abs:"energy" AND abs:"LLM inference"`, 25 results
  → 2601.22362 (Delavande/Luccioni), 2512.03024 (TokenPowerBench), plus ~15 edge/NPU/accelerator papers
- `abs:"speculative decoding" AND abs:"energy"`, 20 results → 2602.09113 (Dutta, EACL Findings 2026)
- `abs:"rebound effect" AND abs:"AI"`, 25 results → only 2501.16548 (Jan 2025) and 2510.09022; nothing 2026
- `all:"MLPerf"`, 25 results → nothing 2026 on MLPerf Power; the benchmark paper is 2410.12032 (Oct 2024)
- `abs:"H100" AND abs:"energy" AND (abs:"B200" OR abs:"Blackwell" OR abs:"A100")`, 25 results
  → 2604.10852 (xPU-athalon), 2601.22076 (Where do the joules go), 2603.17280 (1/W law), 2605.23918
    (model parking tax), 2609.10550 (deployment stack)
- `abs:"energy reporting" AND abs:"AI"` — thin, 5 results
- `abs:"energy measurement" AND abs:"large language model"` → 2603.15699 (time as energy proxy),
  2601.22357 (energy cost of thanking AI)
- `abs:"LLM" AND abs:"energy" AND (abs:"logistic regression" OR abs:"classical machine learning" OR
  abs:"smaller models")` → 2601.08844 (SLM vs LLM emissions), 2504.13217 (LLM right-sizing)
- `abs:"carbon" AND abs:"task-specific" AND abs:"language model"` → 2506.00200 (radiology, lightweight)

### OpenAlex
- `reasoning models inference energy consumption`, from_publication_date 2025-09-01, cited_by desc
  → almost entirely off-topic surveys. OpenAlex is not useful for this area; arXiv is where the work is.

### WebSearch / WebFetch
- "Wright Igel Samuel Efficiency Is Not Enough sustainable AI arXiv full text" → found arXiv 2309.02065,
  full PDF retrieved and read (879 lines of text). Also surfaced 2511.15259 (Wiesner et al.) and
  2509.20241 (Oviedo et al., Joule).
- "MLPerf Inference v6.0 2026 power results energy per query results" → MLCommons v6.0 (2026-04) and
  v6.1 (2026-09) results pages exist; fetched v6.1 page — no power/energy figures published in the
  announcement, only a general statement about energy efficiency as a goal.
- "2026 data center rack power density AI accelerator performance per watt" → secondary sources only
  (DataCenterKnowledge, vendor blogs, AFCOM report quoted at second hand). Not usable under the brief's
  journalism rule without the underlying AFCOM document.
- Full PDFs downloaded and text-extracted: 2509.20241, 2605.01158, 2601.22362, 2604.10852, 2309.02065;
  first pages of 2605.23926, 2606.21428, 2601.22076 for affiliations.

## Duplicate checks (grep -ril over /research/)
Strubell (2 hits, different papers), Morrison (0), Olmo (0), Vandenbergh (0), MLPerf (0), Oviedo (0),
Kazhamiaka (0), Bianchini (0), Wiesner (0), "test-time" (0), "reasoning model" (0), "speculative" (0),
TokenPowerBench (0), Blackwell (0), GB200 (0), "performance per watt" (0), "small language model" (0).
Jevons/rebound: ghg/018, water/023 (Wright), narrative/003, ghg/002, ghg/013 (Tomlinson).
Choukse: frugal/012 (DynamoLLM — same Microsoft group as 017, different paper).
Zhai: frugal/009 is a *different* Zhai (AI overreliance, 2024), not the 2026 reasoning-redundancy author.
No duplicates written.

## Reviewed and rejected
- **2511.15259** Wiesner, O'Neill, Larosa & Kao, "Efficiency Will Not Lead to Sustainable Reasoning AI".
  Fetched the PDF. Assertion with no new data — the exact failure mode the brief's rule 1 bans and that
  the Wright correction is fixing. Mentioned inside 026 rather than given its own file.
- **2601.00823** "Energy-Aware Routing to Large Reasoning Models" (Ellis-Mohr, Hartman, Varshney) —
  theoretical, no measurements.
- **2603.17280** "The 1/W Law" — good framing (tok/W halves per context doubling; H100→B200 = 1.7x vs
  routing = 2.5x) but explicitly states "no new hardware experiments were conducted"; B200/H200 figures
  are ±20% analytical projections. Cited inside 023 rather than written up.
- **2608.28667** GreenBench (Apple M4 Pro) and **2609.11940** (mobile battery) — edge single-user, not
  production fleets.
- **2512.03024** TokenPowerBench — a tool paper; 025 (Chung et al.) covers the same territory with far
  more measured configurations and includes B200.
- **2608.11226** Curcio, RL power control of training — measured and interesting (26.2% tokens/MWh gain
  at 7B, null result at 72B), single-author preprint, and the fleet claims are simulated from a composed
  16-GPU set. Borderline; dropped for space.
- **2605.23918** "Model Parking Tax" — real production telemetry (335k samples, 14 H100s), but the finding
  (idle power is set by CUDA context, not VRAM) is narrow. Next in line if the folder wants an 11th.
- **2601.08844** Garg et al., SLM vs LLM emissions — SLMs matched LLMs on 4 of 6 tasks. Would have been
  the priority-3 file; dropped because 019 and 017 both already carry the right-sizing argument with
  better-specified energy accounting.

## Came up empty
- **2026 empirical rebound/Jevons work on AI.** Nothing. The literature is all 2024-2025 position papers
  (2501.16548, 2510.09022) or assertion (2511.15259). This remains the corpus's weakest claim.
- **MLPerf Power 2026 results.** v6.0 and v6.1 shipped in 2026 with a power category, but MLCommons
  publishes no summary energy figures in its announcements and does not normalise to joules per token.
  Extracting comparable numbers would require parsing the raw submission tables.
- **A 2026 energy-reporting standard.** Nothing found. The EU AI Act transparency work (2409.07471) is
  2024 and belongs in /policy/.
- **Documented cases where a classical method matched an LLM at a fraction of the energy** (priority 7).
  The closest hits are 2506.00200 (radiology report structuring with lightweight models, May 2025) and
  /research/frugal/010 (TabPFN / gradient-boosted trees, already in the folder). Neither reports energy.
  This priority is genuinely unserved by the 2026 literature.
- **Absolute rack power rising alongside per-token efficiency**, from a primary source. Vendor and trade
  press only. Needs an AFCOM State of the Data Center 2026 copy or an OCP specification.

## Remaining gaps for whoever picks this up
1. Rebound with data, not assertion. Candidate approach: token-volume disclosures (Google/OpenAI public
   statements) against per-token efficiency improvements over the same window.
2. MLPerf Power v6.0/v6.1 raw submission tables — the only standardised, audited AI energy figures that
   exist, and the repo has none of them.
3. FP4 on Blackwell. Everything measured here is FP8/INT8 on Hopper or older. 021's INT8 penalty
   explicitly should not be generalised to hardware-native FP4.
4. Agentic workloads. 017 excludes tool calling and orchestration by construction; 020 tests maths only.
   Multi-turn agent energy is unmeasured anywhere in this corpus.

---

### Narrative research log — 2026-09-19

Area: "AI will help the climate" narrative, scrutinised. Files 021–029 written to research/narrative/.

## Searches run

### arXiv (API, phrase-quoted, filtered to submissions >= 2025-09)
- `all:"avoided emissions"` — 5 hits in window. Yielded 2609.18029 (Xu, time-aware framework → 029) and 2604.26539 (Roussilhe, ICT/O&G → 027).
- `abs:"rebound effect" AND abs:"artificial intelligence"` — 0 hits in window.
- `all:"interconnection queue"` — 3 hits: 2609.10455 (Heidari, queue cascade vulnerability), 2608.08170 (on-site power), 2605.14714 (siting). All grid/policy-folder territory, none quantifies AI displacing electrification. Not used.
- `abs:"AI for sustainability" OR abs:"AI for climate"` — 16 hits. Yielded 2606.23192 (Kunkel, "AI against sustainability", cited inside 027), 2606.04214 (Gujral et al., efficiency claims as greenwashing — left for the washing folder), 2606.09006, 2605.26076 (not used).
- `ti:"systematic review" AND abs:"environmental impact of AI"` — 0 hits.
- `abs:"reinforcement learning" AND abs:"HVAC" AND abs:"deployment"` — 6 hits. Yielded 2609.05314 (Neubauer/LBNL, LLM-HVAC deployment readiness → 025).
- Direct id_list lookups: 2602.24091 (Carmeno → 028), 2607.04016 (He → 026), 2603.01198 (Jadhav digital twin — simulation only, not used), 2501.15085 (Zhan, ICLR 2025, production DC offline RL, 14–21% cooling savings over 2000 h — real deployment but Jan 2025, outside the recency window; cited as context only), 2606.23452 (Lee, ERCOT bilevel allocation — conclusion is about congestion, not displacement; not used).

### OpenAlex
- `search=avoided emissions accounting consequential life cycle`, `from_publication_date:2025-09-01` — full-text search too noisy, no usable hits.
- `search=artificial intelligence climate mitigation net impact review` — same, noise.
- Title search `comparison of methodologies for avoided emissions quantification` — found O'Keeffe & Brander 2026, DOI 10.1016/j.jclepro.2026.147672, OA hybrid → 023. (Note: the sciencedirect PII from web search resolved to a different, wrong DOI; OpenAlex gave the correct one.)

### WebSearch
- "IEA Energy and AI report avoided emissions scenario 1.4 Gt widespread adoption" → IEA chapter, retrieved directly by curl and text-extracted → 021.
- "Google 2026 environmental report AI avoided emissions claim methodology counterfactual" → PDF (18 MB) downloaded, pdftotext, endnotes 100–153 read → 022, 024.
- "Microsoft 2026 sustainability report AI avoided emissions customers carbon" → PDF (14 MB) downloaded and extracted. Only one mention of "avoided" in the whole report, and it covers four internal initiatives (Xbox efficiency, CFE, sustainable fuels, Surface supply chain), not AI-for-climate. Used as contrast inside 022.
- "DeepMind data centre cooling 40% claim never independently verified 2026" and "Google data center AI cooling energy savings verified replication 2026" → no independent verification found; DeepMind 2016 blog retrieved directly → 024.
- "data centers displace electrification grid capacity opportunity cost 2026" → nothing quantitative on displacement.
- "2026 systematic review environmental impact artificial intelligence meta-analysis" → Carmeno et al. → 028.

### Serper (Google Scholar, qdr:y)
- "AI climate solutions evidence gap deployment verified savings 2026" — all IGI-Global/MDPI review chapters, no primary evidence. Empty.
- "data center load growth crowding out electrification decarbonization clean energy opportunity cost" — empty for the specific question.
- "DeepMind data center cooling 40% claim critique evidence" — only theses and SSRN preprints; nothing citable.

## Duplicate checks run before writing
`grep -ril` across the whole research/ tree for: Roussilhe, "own goals", "divergent net energy", Xu, "time-aware", Akinci, Neubauer, Carmeno, O'Neill, Gujral, Kunkel, Brander, "avoided emissions", "Energy and AI", DeepMind, "environmental report", "offline reinforcement", "cooling system optimization", arXiv ids. All clear. Note: the repo had **no** IEA *Energy and AI*, no Google or Microsoft environmental report, and no DeepMind material at all before this pass.

## Came up empty
- **Independent verification of the DeepMind 40% cooling claim.** Does not exist, ten years on. Recorded as a negative finding in 024.
- **Priority 5, opportunity cost / allocation.** No 2026 source quantifies clean generation or interconnection capacity allocated to AI displacing electrification of heating, transport or industry. The nearest candidates are Lee et al. 2026 (arXiv 2606.23452, ERCOT bilevel siting — competition for electricity is stated but the result is about congestion cost, not displacement) and Heidari 2026 (arXiv 2609.10455, LBNL queue data: 8 200 projects, 2 061 GW queued, only 13% of 2000–2020 capacity reaching operation — real data, but not disaggregated by load type or by what the data-centre share displaces). Neither supports the claim. Recommend the policy or datacenters researcher take the queue data on its own terms.
- **Measured at-scale AI deployments with before/after data and AI energy cost included, 2026.** None found. The closest real-world result is Zhan et al. ICLR 2025 (14–21% cooling savings, 2 000 h, production DC) which is out of window and does not net the training/inference cost of the controller.

---


## 2026-01-16 (Continued)

### Narrative - 2025 AI for Climate Net Environmental Impact Research

**OpenAlex Searches Performed:**
1. "AI climate environmental benefit" (2025 filter) - 15 results, mostly agriculture/plant papers
2. "AI sustainability net impact" (2025 filter) - 15 results, general sustainability papers
3. "machine learning climate solution" (2025 filter) - 15 results, general papers
4. "AI carbon footprint environmental impact" (2025 filter) - 15 results, **FOUND: Making AI Less Thirsty (31 citations)**
5. "generative AI sustainability environmental" (2025 filter) - 15 results, general papers
6. "AI decarbonization climate mitigation" (2025 filter) - 15 results, **FOUND: AI energy transition review (128 citations)**
7. "LLM carbon emission environmental trade-off" (2025 filter) - 15 results, **FOUND: Energy costs of communicating with AI (4 citations), AI climate resilience systematic review (6 citations)**
8. "AI IoT environmental monitoring" (2025 filter) - **FOUND: 77 citations paper**
9. "AI wastewater treatment environmental" (2025 filter) - **FOUND: 26 citations paper**

**Key Findings (2025 Publications Only):**
- Dauner & Socher (2025) in Frontiers in Communication: Direct measurement of LLM accuracy-emissions trade-off; 14 models tested, larger reasoning models achieve 84.9% accuracy but "substantially higher emissions"
- Frontiers in Climate (2025): Systematic review of 385 AI-climate papers; 64.4% focus on adaptation, only 16% on mitigation; Africa/South America underrepresented
- Electronics (2025): AI+IoT for environmental monitoring; 77 citations; acknowledges benefits but also "substantial obstacles" including data quality, security, ethics
- Water (2025): AI in wastewater "almost all applications involve predictive studies, often at small scale or with limited data"; significant barriers to real deployment

**Excerpts Created:**
- `/research/narrative/017-energy-costs-communicating-ai-2025.md` - LLM accuracy vs emissions trade-off (empirical study)
- `/research/narrative/018-ai-climate-resilience-systematic-review-2025.md` - 385-paper review: adaptation dominates (64.4%), mitigation neglected (16%)
- `/research/narrative/019-ai-iot-environmental-monitoring-2025.md` - AI+IoT potential with acknowledged obstacles
- `/research/narrative/020-ai-wastewater-treatment-limits-2025.md` - Critical assessment of AI in wastewater; mostly studies, few deployments

**Key 2025 Net Impact Insights:**
1. **Trade-off is real and quantified** - Larger, more capable LLMs = substantially higher emissions (Dauner 2025)
2. **AI climate research favors adaptation over mitigation** - 4:1 ratio; if AI helps us cope with climate change rather than prevent it, "AI will save the climate" narrative is misplaced
3. **Regional disparities persist** - Africa, South America underrepresented in AI climate research despite being most vulnerable
4. **Implementation gap** - AI environmental applications remain mostly "predictive studies," not real deployments (Water 2025)
5. **Substantial barriers identified** - Data quality, interoperability, security, ethics, incentives

**Notes:**
- 2025 literature shows increasingly nuanced view of AI-for-climate claims
- Empirical measurements of emissions trade-offs emerging
- Systematic reviews reveal bias toward adaptation over mitigation
- Critical assessments highlighting barriers to real-world AI environmental benefit
- Gap: AI's own environmental footprint still rarely factored into benefit assessments
- Gap: Rebound effects and opportunity costs remain unaddressed

---

### Greenwashing/ESG Reporting - 2025 Publications Focus

**OpenAlex Searches Performed:**
1. "greenwashing ESG disclosure" filter:2025 - 15 results, found AI for sustainability paper, disclosure fog paper, ESG greenwashing TISM paper
2. "carbon neutral claims verification" filter:2025 - 15 results, mostly unrelated (materials science papers)
3. "sustainability reporting quality" filter:2025 - 15 results, found green hydrogen gap paper
4. "greenwashing corporate sustainability" filter:2025 - 15 results, **FOUND: Forliano et al. landscape paper (29 citations), Xu et al. market value paper (26 citations), Zervoudi case studies paper (24 citations)**
5. "ESG reporting quality disclosure" filter:2025 - 15 results, **FOUND: Al Amosh accounting complexity paper (12 citations)**
6. "climate disclosure corporate emissions" filter:2025 - 15 results, found Lancet 2025 report, confirmed Jiang et al. 2025 already captured
7. "greenwashing detection AI NLP" filter:2025 - 10 results, **FOUND: ACL paper on robust ESG analysis (1 citation)**
8. "ESG greenwashing verification audit" filter:2025 - 10 results, **FOUND: Sneideriene impression management gap paper (1 citation)**

**Key Findings (2025 ONLY):**
- Forliano et al. (2025) in Review of Managerial Science: Systematic review of 97 papers identifies 4 thematic clusters; macro-level theories (legitimacy, institutional, stakeholder) dominate - greenwashing is systemic response to institutional pressures, not individual misbehavior (29 citations)
- Zhu, Fan & Zheng (2025) in IJFE: "Disclosure Fog" - institutional investors inadvertently facilitate greenwashing; pressure-sensitive investors most problematic; post-2016 Green Financial System guidance reduced this effect (10 citations)
- Zervoudi, Moschos & Christopoulos (2025) in Sustainability: Comprehensive CSR-to-ESG-to-Greenwashing review with case studies (VW, Zara, Coca-Cola, BP) showing systemic patterns (24 citations)
- Al Amosh (2025) in CSREM: Complex accounting structures enable selective ESG disclosure; 5,146 US firm-year observations show environmental disclosures most affected (12 citations)
- Sneideriene & Legenzova (2025) in Sustainability: Novel textual analysis method detects greenwashing via "impression management gap" between sustainability and financial reports; regulatory pressure did NOT reduce gaps (1 citation)

**Excerpts Created:**
- `/research/washing/012-forliano-2025-greenwashing-landscape.md` - Multi-level theoretical framework for greenwashing
- `/research/washing/013-zhu-2025-disclosure-fog-investors.md` - Institutional investors and greenwashing
- `/research/washing/014-zervoudi-2025-greenwashing-case-studies.md` - Case studies of major corporate greenwashing
- `/research/washing/015-alamosh-2025-accounting-complexity-esg.md` - Accounting complexity enables selective disclosure
- `/research/washing/016-sneideriene-2025-greenwashing-textual-detection.md` - Textual analysis detection method

**Notes:**
- Strong 2025 academic literature on greenwashing mechanisms and detection
- Limited 2025 papers specifically on AI/tech company environmental claims
- Key theme: Greenwashing is systemic (institutional pressures) not individual (bad actors)
- Key theme: Regulatory pressure alone insufficient to reduce greenwashing (Sneideriene finding)
- Key theme: Complex corporate structures enable selective disclosure (Al Amosh finding)
- Key theme: Investors with business relationships are unreliable watchdogs (Zhu finding)
- Gap: No 2025 peer-reviewed papers specifically analyzing tech company carbon/water claims
- Gap: AI/NLP greenwashing detection methods emerging but not yet applied to tech sector at scale

---

## 2026-01-16

### GHG Emissions - 2025 AI/LLM Carbon Emissions Research

**OpenAlex Searches Performed:**
1. "LLM energy consumption carbon" (2025 filter) - 15 results, **FOUND: Li 2025 CACM, Hardware accelerators survey, Energy-efficient transformer inference**
2. "generative AI environmental impact" (2025 filter) - 15 results, general papers
3. "deep learning energy efficiency" (2025 filter) - 15 results, general papers
4. "neural network carbon footprint" (2025 filter) - 15 results, general papers
5. "Luccioni AI emissions energy" (2025 filter) - 10 results, **FOUND: "Efficiency Is Not Enough" CACM paper, "Energy costs of communicating with AI", Understanding Environmental Impact GenAI**
6. "AI carbon emissions sustainability" (2025 filter) - 15 results, general papers
7. "sustainable AI computing green machine learning" (2025 filter) - 15 results, general papers
8. "ChatGPT carbon footprint emissions" (2025 filter) - 10 results, general papers
9. "data center power usage electricity AI" (2025 filter) - 15 results, general papers

**Key Findings (2025 Publications Only):**
- Wright, Igel & Samuel (2025) in Communications of the ACM: "Efficiency Is Not Enough" - argues efficiency-first approach is insufficient for sustainable AI; systemic factors may overwhelm efficiency gains
- Dauner & Socher (2025) in Frontiers in Communication: Empirical measurement of 14 LLMs (7-72B parameters) on A100 GPU; quantifies accuracy-emissions trade-off; token output is major emissions driver
- Rozycki, Solarska & Waligora (2025) in Energies: Review of energy-aware ML techniques; finds embodied emissions often eclipse operational; calls for dual strategy (operational + manufacturing)
- Kachris (2025) in Applied Sciences: Hardware accelerator survey covering GPUs, FPGAs, custom ASICs for LLM energy efficiency
- Berthelot et al. (2025): Already covered in previous search (006)

**Excerpts Created:**
- `/research/ghg/018-wright-2025-efficiency-not-enough.md` - Efficiency-first approach insufficient for sustainable AI
- `/research/ghg/019-dauner-2025-energy-costs-communicating-ai.md` - Empirical LLM energy measurement (14 models, A100 GPU)
- `/research/ghg/020-rozycki-2025-energy-aware-ml-models-review.md` - Embodied vs operational emissions, dual strategy
- `/research/ghg/021-kachris-2025-hardware-accelerators-llm-survey.md` - Hardware accelerator energy efficiency survey

**Key 2025 Insights:**
1. **Efficiency alone is insufficient** - Wright et al. (2025) argues systemic factors (scale, rebound) overwhelm efficiency gains
2. **Embodied emissions matter** - Rozycki et al. (2025) finds hardware manufacturing emissions can exceed operational emissions
3. **Accuracy-emissions trade-off quantified** - Dauner & Socher (2025) measures 14 LLMs; larger reasoning models achieve 84.9% accuracy but at substantially higher emissions
4. **Token output drives emissions** - More verbose AI responses = higher emissions (Dauner & Socher 2025)
5. **Hardware selection critical** - Different accelerators (GPU vs FPGA vs ASIC) have different efficiency profiles (Kachris 2025)

**Notes:**
- 2025 literature shows maturing discourse on AI sustainability
- Shift from efficiency-only focus to systemic and lifecycle perspectives
- Empirical measurement studies emerging (Dauner & Socher provides actual A100 measurements)
- Embodied emissions gaining attention alongside operational emissions
- Gap: Still limited per-query emissions data for production AI services

---

### Data Centers - 2025 Publications Search (Energy & Sustainability)

**OpenAlex Searches Performed:**
1. "data center energy efficiency sustainability" (2025 filter) - 15 results, mostly unrelated (batteries, catalysts)
2. "hyperscale data center power" (2025 filter) - 15 results, **FOUND: Lei et al. CBECS, Rollinson off-grid, Lord HPC waste, Setyo thermal review**
3. "AI data center infrastructure" (2025 filter) - 15 results, mostly general AI/healthcare papers
4. "data center cooling energy consumption" (2025 filter) - 15 results, mostly unrelated
5. "AI training energy carbon data center" (2025 filter) - 15 results, **FOUND: Li 2025 "Making AI Less Thirsty" already captured**

**Key Findings:**
- Lei et al. (2025): CBECS data shows US small/midsize DCs declining (1.764M to 1.398M), but identifies PUE-WUE tradeoff - more energy-efficient facilities are more water-intensive due to water-cooled chillers
- Rollinson et al. (2025): Off-grid hybrid renewable/gas microgrids for hyperscale DCs beat grid equivalents on BOTH cost and emissions across European hotspots (Frankfurt, London, Amsterdam, Paris, Dublin)
- Lord et al. (2025): CHI paper documenting how academic institutions (conferences, funders, universities) "reinforce and embed, rather than challenge, expectations of growth and waste" in HPC
- Setyo et al. (2025): Literature review finds average PUE of 2.23 across studies - significantly worse than hyperscaler claims of 1.1-1.4; average IT power only 44.8% of total

**Excerpts Created:**
- `/research/datacenters/012-lei-2025-us-small-midsize-dc-cbecs.md` - CBECS survey on US data centers, PUE-WUE tradeoff
- `/research/datacenters/013-rollinson-2025-offgrid-hyperscale-feasibility.md` - Off-grid renewable feasibility study
- `/research/datacenters/014-lord-2025-hpc-waste-academia.md` - Critical analysis of institutional growth drivers
- `/research/datacenters/015-setyo-2025-dc-energy-efficiency-thermal-review.md` - PUE measurement literature review

**Notes:**
- 2025 literature on data center energy is still emerging (few citations on most papers)
- Most high-citation 2025 papers from OpenAlex are unrelated to data centers (chemistry, batteries, health)
- Commins & Irion 2025 (EU policy) already captured in previous search
- Key insight from Setyo: Self-reported hyperscaler PUE (1.1-1.4) may not be representative of actual industry average (2.23)
- Lord et al. provides rare sociological analysis of WHY compute demand keeps growing despite efficiency gains

---

### Water Consumption Numbers Compilation (Quantitative Data Focus)

**OpenAlex Searches Performed:**
1. "AI water consumption liters gallons" - 15 results, mostly biofuel/general papers
2. "ChatGPT water footprint per query" - 15 results, found ChatGPT failures paper (401 citations)
3. "data center water usage WUE" - 15 results, general environmental papers
4. "machine learning water consumption" - 15 results, general ML papers
5. "GPT training water evaporated" - 15 results, **FOUND: Li et al. 2023 (138 citations), Li 2025 CACM (31 citations)**
6. "large language model environmental impact carbon water" - 15 results, general papers
7. "generative AI water footprint environmental" - 15 results, general papers
8. "data center cooling water efficiency PUE" - 15 results, **FOUND: liquid cooling paper (118 citations)**
9. "Microsoft Google data center sustainability water" - 15 results, general papers
10. "power usage effectiveness data center water cooling" - 15 results, general papers
11. "evaporative cooling water server consumption" - 15 results, **FOUND: liquid cooling necessity paper**
12. "GPT-4 BLOOM Llama carbon water environmental cost" - 10 results, **FOUND: Li 2025 CACM**
13. "LLM energy consumption watt joule inference" - 15 results, **FOUND: Google 2025 AI environmental impact paper**
14. "Luccioni emissions AI energy" - 10 results, **FOUND: Green AI systematic review (205 citations)**
15. "Reducing carbon impact generative AI inference" - 10 results, **FOUND: Chien et al. 2023 (106 citations)**
16. "Green AI energy efficiency systematic review" - 10 results, **FOUND: Verdecchia et al. 2023 (205 citations)**
17. "Environmental equity AI geographical load balancing" - 10 results, **FOUND: Li et al. 2023 equity paper**

**Key Findings:**
- Li et al. (2023/2025): Seminal paper - GPT-3 training evaporates ~700,000 liters; ChatGPT 500mL per 20-50 queries (10-25mL/query); 4.2-6.6B m3 global AI by 2027
- Elsworth et al. (2025 - Google): First production measurement - Gemini Apps 0.26 mL water per prompt, 0.24 Wh energy - CONTESTED vs Li estimates
- Li et al. (2023): Environmental inequity - AI footprint disproportionately higher in certain regions
- Chien et al. (2023): ChatGPT carbon/energy projections to 2035, request routing strategies
- Verdecchia et al. (2023): Green AI systematic review - 98 papers, energy savings up to 115%

**Excerpts Created:**
- `/research/water/017-google-2025-gemini-water-measurements.md` - Google's first production measurement (0.26 mL/prompt)
- `/research/water/018-li-2025-cacm-ai-water-projections.md` - Key water consumption numbers (CACM peer-reviewed)
- `/research/water/019-li-2023-environmental-equity-regional-water.md` - Regional disparities in water footprint
- `/research/water/020-chien-2023-genai-inference-carbon-projections.md` - ChatGPT carbon/energy projections
- `/research/water/021-verdecchia-2023-green-ai-systematic-review.md` - Green AI review (115% energy savings)

**Critical Finding: Contested Estimates:**
- Li et al. 2023/2025: 10-25 mL per ChatGPT query
- Google 2025: 0.26 mL per Gemini prompt (40-100x lower)
- Discrepancy requires independent verification
- Google has obvious conflict of interest in reporting lower numbers

**Notes:**
- Google paper (Elsworth et al. 2025) is first production-environment measurement of AI serving water
- Li et al. work upgraded from arXiv to Communications of the ACM (peer-reviewed)
- Environmental inequity dimension added by Li et al. 2023 equity paper
- Green AI energy savings (up to 115%) translate to proportional water savings
- Gap: Still no independent verification of corporate claims

---

### Water Consumption - Reuse/Recycling Research (Data Center Water Reuse Practices)

**OpenAlex Searches Performed:**
1. "data center water recycling" - 10 results, mostly unrelated general papers
2. "cooling water reuse data center" - 10 results, general papers
3. "wastewater treatment data center" - 10 results, general environmental papers
4. "water efficiency data center WUE" - 10 results, agriculture/plant papers dominated
5. "greywater recycling industrial cooling" - 10 results, **FOUND: sustainable wastewater reuse, recycled water systems**
6. "data center water consumption cooling" - 15 results, general papers
7. "AI water consumption data center" - 15 results, general AI papers
8. "sustainable data center cooling" - 15 results, general papers
9. "holistic sustainable computing" - 10 results, found ESC framework paper
10. "making AI less thirsty" - 5 results, **FOUND: Li et al. 2025**
11. "water reuse comprehensive review" - 10 results, **FOUND: Florides et al. 2024**
12. "recycled water systems building" - 10 results, **FOUND: Chen et al. 2024**
13. "cooling tower blowdown water reuse" - 10 results, **FOUND: Muller et al. 2024, Biedunkova et al. 2024**
14. "industrial water reuse zero liquid discharge" - 10 results, general papers
15. "membrane bioreactor wastewater reclamation" - 10 results, **FOUND: Kim et al. 2024**

**Key Findings:**
- Florides et al. (2024): Comprehensive water reuse review - covers legislative frameworks, recovery methods, public perception
- Chen et al. (2024): Recycled water in buildings - greywater recycling technologies, 12-14% efficiency gains, membrane filtration
- Muller et al. (2024): Cooling tower blowdown reuse achieves 13% water savings - directly applicable to data centers
- Biedunkova et al. (2024): Operating power plant achieves 25% blending of treated CTBD with make-up water
- Kim et al. (2024): Hybrid MBR systems for wastewater reclamation - FO/MD for low-energy water recycling

**Excerpts Created:**
- `/research/water/012-florides-2024-water-reuse-comprehensive.md` - Comprehensive water reuse review
- `/research/water/013-chen-2024-recycled-water-buildings.md` - Recycled water systems for buildings
- `/research/water/014-muller-2024-cooling-tower-blowdown.md` - Cooling tower blowdown reuse (13% savings)
- `/research/water/015-biedunkova-2024-cooling-water-reuse-power-plant.md` - Power plant water reuse (25% blending)
- `/research/water/016-kim-2024-membrane-bioreactor-wastewater.md` - Membrane bioreactor technologies

**Notes:**
- Limited peer-reviewed papers specifically on data center water reuse/recycling practices
- Most relevant papers address industrial cooling (power plants) rather than data centers specifically
- Cooling tower blowdown reuse most directly applicable to data center evaporative cooling
- Key technologies: lime softening, membrane filtration, reverse osmosis, forward osmosis, membrane distillation
- Achievable water savings: 13-25% through blowdown reuse and treatment
- Gap: No peer-reviewed papers on specific tech company (Google, Microsoft, Meta) water recycling programs
- Gap: Limited data center-specific WUE (Water Usage Effectiveness) measurement standards
- Gap: On-site treatment vs. municipal water source trade-offs not well-studied for data centers

---

### Washing Claims Research (Greenwashing/Bluewashing in Tech/AI)

**OpenAlex Searches Performed:**
1. "tech greenwashing carbon neutral" - 10 results, found ESG/AI papers
2. "data center renewable energy claims" - 10 results, mostly technical papers
3. "corporate sustainability reporting AI" - 10 results, found ESG reporting papers
4. "PPA renewable energy criticism" - 10 results, limited direct relevance
5. "greenwashing corporate claims" - 15 results, strong findings including carbon offsets paper
6. "carbon offset criticism validity" - 10 results, found carbon farming paper
7. "voluntary carbon market criticism" - 10 results, found relevant papers
8. "AI environmental footprint sustainability" - 10 results, found ecological footprint paper
9. "ESG greenwashing detection" - 10 results, found greenwashing incidents paper

**Key Findings:**
- Trencher et al. (2024) in Nature Communications: Major companies purchase low-quality carbon offsets
- Frontiers in Sustainability (2024): Systematic review of greenwashing in sustainable finance
- Geography Compass (2024): Critical analysis of greenwashing in green capitalism
- Gunther et al. (2024): Carbon farming overestimates negative emissions
- Wang et al. (2024): AI's complex impact on ecological footprints

**Excerpts Created:**
- `/research/washing/001-trencher-2024-carbon-offsets.md`
- `/research/washing/002-greenwashing-sustainable-finance-2024.md`
- `/research/washing/003-de-freitas-netto-2024-green-capitalism.md`
- `/research/washing/004-gunther-2024-carbon-farming-emissions.md`
- `/research/washing/005-kereszturi-2024-greenwashing-incidents.md`
- `/research/washing/006-wang-2024-ai-ecological-footprint.md`
- `/research/washing/007-raman-2024-green-sustainable-ai.md`

**Notes:**
- Serper API key not available for news search
- Limited direct papers on tech-specific "100% renewable" claims or "water positive" pledges
- Most academic research focuses on general corporate greenwashing rather than tech-specific cases
- Carbon offset criticism was the strongest area of academic coverage

---

### Washing Gaps Research - Corporate Environmental Disclosure Gaps

**OpenAlex Searches Performed:**
1. "corporate environmental disclosure gaps" - 10 results, found ESG papers
2. "sustainability reporting limitations tech" - 10 results, general papers
3. "Scope 3 emissions disclosure challenges" - 10 results, found ESG challenges paper
4. "ESG reporting transparency gaps" - 10 results, found greenwashing papers
5. "carbon accounting limitations" - 10 results, general papers
6. "greenwashing corporate disclosure" - 10 results, found cheap talk paper, offset paper
7. "carbon footprint reporting incomplete" - 10 results, general papers
8. "climate disclosure cheap talk" - 10 results, **FOUND: Bingler et al. 2024 ClimateBert paper**
9. "carbon offset quality low" - 10 results, **FOUND: Trencher et al. 2024 low-quality offsets**
10. "ESG rating divergence inconsistency" - 10 results, found ESG regulation papers
11. "Limited accountability emissions targets" - 10 results, **FOUND: Jiang et al. 2025 Nature Climate Change**
12. "greenwashing incidents detection" - 10 results, **FOUND: Kereszturi et al. 2024 incident-based**

**Key Findings:**
- Bingler et al. (2024) in J. Banking & Finance: "Cheap talk" in climate disclosures - voluntary disclosure associated with MORE greenwashing, not less
- Jiang et al. (2025) in Nature Climate Change: 9% of emissions targets failed, 31% "disappeared" - only 3 failures got media coverage
- Chopra et al. (2024) in Sustainability: ESG reporting quality concerns - lack of standardization, company-centric bias
- Kereszturi et al. (2024) in CSR & Env. Management: Incident-based greenwashing detection - 7% of MSCI World companies engaged in greenwashing

**Excerpts Created:**
- `/research/washing/008-bingler-2024-climate-cheap-talk.md` - Climate disclosure cheap talk vs real action
- `/research/washing/009-jiang-2025-emissions-target-accountability.md` - Limited accountability for failed emissions targets
- `/research/washing/010-chopra-2024-esg-reporting-gaps.md` - ESG reporting systemic gaps
- `/research/washing/011-kereszturi-2024-greenwashing-incidents.md` - Incident-based greenwashing detection

**Notes:**
- Strong academic evidence that voluntary disclosure enables greenwashing rather than preventing it
- Target accountability vacuum: companies rewarded for announcements but not penalized for failures
- ESG scores can improve even while environmental damage occurs
- Incident-based methodology reveals what self-reported ESG data misses
- Gap: Per-query costs and water consumption per AI inference never disclosed by companies
- Gap: Limited academic papers on AI/tech-specific disclosure gaps (focus is on general corporate ESG)
- Key theme: The gap between disclosure quality and quantity is a systemic feature

---

### Water Consumption - Direct Use Research (AI/Data Center Water Footprint)

**OpenAlex Searches Performed:**
1. "AI water consumption" - 10 results, mostly unrelated general papers
2. "data center water usage cooling" - 10 results, general technical papers
3. "ChatGPT water footprint" - 10 results, limited direct results
4. "machine learning water consumption" - 10 results, general ML papers
5. "generative AI water footprint" - 15 results, found green AI paper
6. "large language model water consumption" - 15 results, general LLM papers
7. "data center environmental impact water" - 15 results, general environmental papers
8. "making AI less thirsty water" - 10 results, **FOUND: Li et al. 2023 seminal paper**
9. "GPT water footprint AI" - 10 results, found more AI papers
10. "green AI sustainable computing" - 15 results, general sustainability papers
11. Papers citing Li et al. 2023 - 15 results, **FOUND: Lehuede 2024, Kocak 2025**
12. "data center cooling evaporative" - 15 results, technical cooling papers
13. "hyperscale data center environmental" - 15 results, **FOUND: Markelius 2024, Chang 2024**
14. "green sustainable AI energy environmental" - 10 results, **FOUND: Bolon-Canedo 2024**

**Key Findings:**
- Li et al. (2023): Seminal paper - GPT-3 training evaporates ~700,000 liters water; ChatGPT "drinks" 500ml per 20-50 queries; projects 4.2-6.6 billion cubic meters AI water demand by 2027
- Lehuede (2024): "Elemental ethics" - documents Chilean communities resisting Google data center and lithium extraction for AI batteries
- Kocak et al. (2025): Healthcare AI sustainability paradox - AI benefits come with environmental costs including water
- Markelius et al. (2024): AI hype "exerts tremendous pressure on finite resources" - explains systemic drivers of consumption growth
- Chang et al. (2024): Data center cooling optimization review - air vs liquid cooling systems, need for standardized efficiency metrics
- Bolon-Canedo et al. (2024): Green AI review - strategies for reducing computational cost (and thus water consumption)

**Excerpts Created:**
- `/research/water/001-li-2023-making-ai-less-thirsty.md`
- `/research/water/002-lehuede-2024-elemental-ethics.md`
- `/research/water/003-kocak-2025-radiology-ai-sustainability.md`
- `/research/water/004-markelius-2024-ai-hype-planetary-costs.md`
- `/research/water/005-chang-2024-data-center-cooling-optimization.md`
- `/research/water/006-bolon-canedo-2024-green-ai-review.md`

**Notes:**
- Li et al. 2023 is THE foundational paper for AI water consumption research
- Limited papers with specific liters-per-query measurements beyond Li et al.
- Most water-related papers focus on data centers broadly, not AI-specific workloads
- Regional variation in water consumption is acknowledged but poorly documented in peer-reviewed literature
- Corporate disclosure data (Microsoft, Google, Meta) not yet well-analyzed in academic literature

---

### Data Center Power Sources Research

**OpenAlex Searches Performed:**
1. "data center renewable energy" - 10 results, mostly unrelated (nanoparticles, batteries)
2. "AI data center power grid" - 10 results, found LLM papers but limited DC-specific
3. "tech company PPA power purchase agreement" - 10 results, found solar industry update
4. "data center nuclear energy" - 10 results, no relevant results
5. "data center electricity consumption carbon" - 15 results, general carbon papers
6. "hyperscale data center energy" - 15 results, found AI hype paper (W4393435592)
7. "corporate renewable energy procurement additionality" - 15 results, found green certificates paper
8. "24/7 carbon free energy matching" - 15 results, limited direct relevance
9. "AI energy consumption training inference" - 15 results, found healthcare AI papers
10. "greenwashing carbon claims corporate" - 15 results, found carbon offsets paper
11. "generative AI environmental impact carbon" - 15 results, found Green AI initiatives paper
12. "data center power usage effectiveness PUE" - 15 results, found cooling and PUE papers
13. "ICT electricity consumption sustainability" - 15 results, found Modern Computing paper
14. "scope 2 emissions electricity carbon accounting" - 15 results, general emissions papers

**Key Findings:**
- Alzoubi & Mishra (2024): 55 green AI initiatives identified, most lack empirical validation
- Trencher et al. (2024): Major companies purchase low-quality carbon offsets (Nature Communications)
- Barbierato & Gatti (2024): Red AI vs Green AI tension - performance vs sustainability
- Kim et al. (2024): PUE varies 1.15-1.43 by climate zone and cooling strategy
- Raman et al. (2024): Three major Green AI research themes, gaps in socio-economic research
- Pazienza et al. (2024): ESC framework for sustainable computing lifecycle

**Excerpts Created:**
- `/research/datacenters/001-alzoubi-2024-green-ai-initiatives.md`
- `/research/datacenters/002-trencher-2024-carbon-offsets-quality.md`
- `/research/datacenters/003-barbierato-2024-red-vs-green-ai.md`
- `/research/datacenters/004-kim-2024-data-center-pue-economizers.md`
- `/research/datacenters/005-raman-2024-green-sustainable-ai-research.md`
- `/research/datacenters/006-pazienza-2024-sustainable-computing-framework.md`

**Notes:**
- Academic literature on DC power claims vs reality is emerging but limited
- Most papers focus on efficiency metrics (PUE) rather than actual grid mix analysis
- Gap: Limited academic papers specifically analyzing PPAs vs actual electrons consumed
- Gap: Few papers on "24/7 carbon-free" vs annual matching distinction
- Gap: Tech company nuclear deals (Three Mile Island) too recent for peer-reviewed literature
- Strong coverage of Green AI concepts but validation of corporate claims lacking

---

### GHG Emissions - Inference (Per-Query Emissions Analysis)

**OpenAlex Searches Performed:**
1. "AI inference energy consumption" - 10 results, general AI review papers
2. "ChatGPT query carbon footprint" - 10 results, limited direct hits
3. "LLM inference emissions" - 10 results, general LLM papers
4. "large language model inference energy" - 10 results, general papers
5. "AI carbon footprint environmental" - 15 results, found Wang et al. ecological footprint paper
6. "machine learning energy efficiency GPU" - 15 results, general ML papers
7. "generative AI electricity consumption" - 15 results, general papers
8. "data center AI energy carbon" - 15 results, found AI energy transition paper
9. "carbon footprint machine learning model" - 15 results, battery/ML papers
10. "energy efficient transformer model" - 15 results, general transformer papers
11. "LLM electricity power consumption" - 20 results, **FOUND: Jiang 2024 chatbot lifecycle, Making AI Less Thirsty, AI hype planetary costs, Green AI survey**
12. "Watt joule GPU transformer inference" - 15 results, **FOUND: Environmental Impact GenAI Services, Tensor-Aware Energy Accounting**
13. "google search query energy comparison" - 15 results, general search papers

**Key Findings:**
- Jiang et al. (2024): LLM chatbots require life-cycle carbon analysis across 8 phases - training, fine-tuning, hardware manufacturing, data management, material recycling
- Li et al. (2025): AI's "secret water footprint" - data centers consume substantial water for cooling
- Markelius et al. (2024): AI hype is "historically unmatched" in planetary costs, exerts tremendous pressure on resources
- Barbierato & Gatti (2024): "Red AI" vs "Green AI" framework - trade-off between accuracy and sustainability
- Wang et al. (2024): At macro level (67 countries), AI reduces ecological footprints but industrial structure moderates benefits
- Berthelot et al. (2025): Specific focus on environmental impact of generative AI services (inference phase)

**Excerpts Created:**
- `/research/ghg/001-jiang-2024-llm-chatbot-lifecycle-footprint.md`
- `/research/ghg/002-li-2025-ai-water-footprint.md`
- `/research/ghg/003-markelius-2024-ai-hype-planetary-costs.md`
- `/research/ghg/004-barbierato-2024-green-ai-survey.md`
- `/research/ghg/005-wang-2024-ai-ecological-footprint-67-countries.md`
- `/research/ghg/006-berthelot-2025-environmental-impact-genai-services.md`

**Notes:**
- Limited peer-reviewed papers with specific grams-CO2-per-query measurements for LLM inference
- Most academic literature focuses on training emissions, not inference/operational emissions
- Per-query estimates in literature are often modeled/calculated rather than measured directly
- Comparison of ChatGPT query to Google search not well-documented in peer-reviewed academic literature
- The "Red AI vs Green AI" framing is gaining traction in sustainability discourse
- Life-cycle analysis (beyond training) is an emerging but still underdeveloped research area

---

### Community Opposition Research (Local Resistance to Data Centers)

**OpenAlex Searches Performed:**
1. "data center community opposition" - 10 results, unrelated papers
2. "data center local resistance" - 10 results, general medical/biology papers
3. "data center environmental justice" - 10 results, general public health papers
4. "data center protest NIMBY" - 10 results, urban air mobility papers
5. "data center water electricity community" - 10 results, general environmental papers
6. "hyperscale data center energy demand" - 10 results, **FOUND: AI hype paper, silicon photonics**
7. "AI infrastructure social impact" - 10 results, general AI papers
8. "power hungry processing watts AI" - 10 results, **FOUND: Luccioni et al. 2024 seminal paper**
9. "data center growth electricity strain" - 10 results, **FOUND: Making AI Less Thirsty 2025**
10. "sustainable AI computing infrastructure" - 10 results, general AI papers
11. "AI sustainability energy environmental" - 10 results, **FOUND: Dhiman et al. 2024 review**
12. "data center water usage scarcity" - 10 results, **FOUND: Global Energy Crisis paper**

**Key Findings:**
- Luccioni, Jernite, Strubell (2024): "Power Hungry Processing" - generative AI orders of magnitude more expensive than task-specific (181 citations)
- Li et al. (2025): "Making AI Less Thirsty" in Communications of the ACM - hidden water footprint (31 citations)
- Markelius et al. (2024): AI hype "historically unmatched" in planetary/social costs; perpetuates socio-economic inequalities
- Dhiman et al. (2024): AI sustainability review - tension between "Sustainability of AI" vs "AI for Sustainability"
- Energies (2024): Global energy crisis heightens tensions between industrial and residential electricity consumers

**Excerpts Created:**
- `/research/community/001-luccioni-2024-power-hungry-ai.md`
- `/research/community/002-li-2025-ai-water-footprint.md`
- `/research/community/003-markelius-2024-ai-hype-costs.md`
- `/research/community/004-dhiman-2024-ai-sustainability-review.md`
- `/research/community/005-global-energy-crisis-2024-efficiency.md`

**Notes:**
- Serper API key not available for news search (would be primary source for specific local opposition cases)
- Academic literature covers environmental/social costs but not specific community resistance cases
- Gap: Local opposition movements (Virginia, Chile, etc.) mainly documented in news media, not peer-reviewed
- Gap: Electricity rate impacts on residential customers not well-studied in AI context
- Gap: Land use and noise concerns from data centers underrepresented in academic literature
- Community opposition stories require news sources (Serper, news archives) rather than academic databases
- Papers found provide academic framing for WHY communities oppose data centers (energy, water, equity)

---

### Narrative Claims Research (AI-for-Climate Critical Analysis)

**OpenAlex Searches Performed:**
1. "AI climate change solution criticism" - 10 results, found green AI papers
2. "AI sustainability benefits rebound effect" - 10 results, mixed relevance
3. "AI environmental efficiency claims" - 10 results, general AI papers
4. "machine learning climate mitigation" - 10 results, general ML papers
5. "Jevons paradox AI" - 10 results, **FOUND: ICT GHG enablement paper, Net Zero dashboards paper**
6. "artificial intelligence carbon footprint environmental cost" - 10 results, general papers
7. "AI energy consumption data center climate" - 10 results, general papers
8. "green AI sustainable computing environmental" - 10 results, general AI papers
9. "ICT GHG enablement emissions reduction" - 10 results, found GHG enablement paper
10. "generative AI environmental impact energy" - 10 results, general papers
11. "large language models energy sustainability" - 10 results, general papers
12. "net zero digital technology emissions" - 10 results, found Global polycrisis paper
13. "AI decarbonization greenwashing" - 10 results, ESG finance papers
14. "ChatGPT GPT environmental footprint emissions" - 10 results, **FOUND: AI hype paper, AI vs human emissions paper**

**Key Findings:**
- Bieser et al. (2024) in Journal of Industrial Ecology: Critical review of telecom industry's GHG "enablement" claims - methodological flaws include cherry-picking beneficial services, ignoring rebound effects
- Markelius et al. (2024): AI hype "historically unmatched" in planetary/social costs, identifies mechanisms fueling overconsumption
- Tomlinson et al. (2024) in Nature Scientific Reports: AI vs human emissions comparison - but explicitly notes it ignores rebound effects
- Gregg & Strengers (2024): Critiques IT sector Net Zero dashboards as creating false sense of progress
- Samuel et al. (2024): Carbon accounting in digital industry requires decision-making under uncertainty - calls for "more data" can delay action
- Moyano-Fernandez et al. (2024): AI-health "honeymoon" should become lasting marriage via environmental justice lens

**Excerpts Created:**
- `/research/narrative/001-bieser-2024-ict-ghg-enablement-critique.md` - ICT industry's flawed GHG enablement claims
- `/research/narrative/002-markelius-2024-ai-hype-planetary-costs.md` - AI hype mechanisms and costs
- `/research/narrative/003-tomlinson-2024-ai-emissions-vs-humans.md` - AI vs human emissions (with rebound effect caveat)
- `/research/narrative/004-gregg-2024-net-zero-dashboards.md` - Critique of IT Net Zero dashboards
- `/research/narrative/005-samuel-2024-carbon-accounting-uncertainty.md` - Carbon accounting uncertainty in digital sector
- `/research/narrative/006-moyano-2024-ai-health-sustainability-honeymoon.md` - AI sustainability and environmental justice

**Notes:**
- Bieser et al. (2024) is key paper for understanding how industry inflates "AI for climate" claims
- The GHG "enablement factor" methodology is widely used but systematically flawed
- Rebound effects (Jevons paradox) explicitly acknowledged as limitation in Tomlinson paper
- Limited academic critique specifically of "AI will save X tonnes CO2" claims - most critique is broader
- Gap: Few papers analyze WHO funds AI-for-climate research (conflict of interest analysis)
- Gap: Limited peer-reviewed analysis of specific tech company claims (Google, Microsoft, etc.)
- The "AI hype" critique (Markelius) connects planetary costs to socio-economic inequality
- Carbon accounting uncertainty paper reveals how calls for "more data" can delay climate action

---

### GHG Emissions - Lifecycle/Embodied (Hardware Lifecycle Analysis)

**OpenAlex Searches Performed:**
1. "GPU manufacturing carbon footprint" - 10 results, general computing papers
2. "AI hardware embodied emissions" - 10 results, general AI papers
3. "server lifecycle emissions" - 10 results, general LLM papers
4. "data center e-waste" - 10 results, unrelated (medical, biology)
5. "semiconductor manufacturing environmental impact" - 10 results, general materials papers
6. "embodied carbon computing hardware" - 15 results, general computing papers
7. "life cycle assessment data center" - 15 results, general LCA papers
8. "chip manufacturing carbon footprint" - 15 results, general materials papers
9. "electronic waste circular economy computing" - 15 results, found recycling papers
10. "server hardware embodied carbon" - 15 results, found Green AI survey
11. "rare earth electronics supply chain environmental" - 15 results, found mineral commodities paper
12. "ICT equipment environmental footprint" - 15 results, found Modern Computing paper
13. "computer hardware sustainability lifecycle" - 15 results, found Industry 5.0 papers
14. "LCA life cycle assessment server computing" - 15 results, **FOUND: Digital content sustainability paper**
15. "carbon footprint machine learning hardware" - 15 results, general papers
16. "AI infrastructure environmental impact manufacturing" - 15 results, general AI papers
17. "sustainable AI computing emissions hardware lifecycle" - 15 results, found Green AI thematic paper
18. "WEEE electronic waste critical materials" - 10 results, found Li-ion battery recycling paper
19. "embodied operational carbon computing" - 10 results, found sustainability papers
20. "generative AI sustainable infrastructure" - 10 results, found Gen AI papers
21. "IT equipment circular economy sustainability" - 15 results, found recycling papers
22. "manufacturing supply chain critical minerals electronics" - 15 results, found material papers

**Key Findings:**
- Istrate et al. (2024) in Nature Communications (59 citations): Environmental sustainability of digital content consumption - includes embodied and operational emissions analysis
- Barbierato & Gatti (2024) in IEEE Access (28 citations): Green AI methodological survey - explicitly addresses hardware innovations as factor in environmental footprint
- Raman et al. (2024) in Journal of Big Data (81 citations): Green/Sustainable AI thematic analysis - emphasizes "AI development lifecycle" integration of sustainability
- Zanoletti et al. (2024) in Batteries (152 citations): Li-ion battery recycling - critical for data center energy storage sustainability
- Psarommatis & May (2024) in Sustainability (56 citations): Digital Product Passport for circularity - applicable to computing hardware lifecycle tracking

**Excerpts Created:**
- `/research/ghg/007-istrate-2024-digital-content-environmental-sustainability.md`
- `/research/ghg/008-barbierato-2024-green-ai-methodological-survey.md`
- `/research/ghg/009-raman-2024-green-sustainable-ai-thematic-analysis.md`
- `/research/ghg/010-zanoletti-2024-lithium-ion-battery-recycling.md`
- `/research/ghg/011-psarommatis-2024-digital-product-passport-circularity.md`

**Notes:**
- Major gap: Limited 2024-2025 peer-reviewed papers specifically quantifying GPU/chip manufacturing embodied emissions
- Academic literature on "Green AI" acknowledges hardware as factor but focuses more on algorithmic efficiency
- "Red AI vs Green AI" framework (Barbierato) gaining traction - includes hardware considerations
- Lifecycle thinking (cradle-to-grave) emphasized but specific data on AI hardware rare
- Battery recycling research applicable to data center UPS/BESS systems
- Digital Product Passport (EU-driven) could enable hardware lifecycle tracking
- Gap: Ratio of embodied vs operational emissions for AI hardware not well-documented in 2024-2025 literature
- Gap: E-waste impacts from AI infrastructure upgrade cycles not specifically studied
- Gap: Rare earth mining impacts for AI hardware not separated from general electronics
- Foundational embodied emissions work (Patterson 2021, Gupta 2022) predates 2024-2025 filter

---

### GHG Training Emissions Research (Additional - Training Focus)

**OpenAlex Searches Performed:**
1. "LLM training carbon emissions" - 10 results
2. "large language model training energy" - 10 results
3. "GPT training environmental impact" - 10 results
4. "AI model training CO2 footprint" - 10 results
5. "AI training electricity consumption carbon" - 10 results
6. "machine learning training emissions" - 10 results
7. "Luccioni AI emissions" - 10 results
8. "power hungry processing carbon" - 10 results
9. "sustainable AI computing energy" - 10 results
10. "carbon footprint artificial intelligence training" - 15 results
11. "deep learning energy consumption sustainability" - 15 results
12. "generative AI environmental cost" - 15 results
13. "neural network training carbon footprint" - 15 results
14. "GPT-4 energy consumption" - 10 results
15. "data center AI carbon emissions" - 10 results
16. "transformer model training emissions estimate" - 10 results
17. "CodeCarbon ML CO2 tracker" - 10 results
18. "efficient transformer environmental" - 10 results
19. "green AI computing training efficiency" - 10 results
20. "foundation model training cost energy" - 10 results
21. "compute carbon machine learning" - 10 results
22. "GPU power consumption deep learning" - 10 results
23. "training cost GPT-3 BERT emissions" - 10 results
24. "data center energy AI workload" - 10 results
25. "machine learning energy measurement methodology" - 10 results
26. "generative AI electricity demand" - 10 results
27. "AI computing sustainability environmental footprint" - 15 results
28. "BLOOM model carbon footprint" - 10 results
29. "model size scaling energy efficiency" - 10 results
30. "Llama training compute carbon" - 10 results

**Key Findings (Training-Specific):**
- Jiang et al. (2024) in Engineering (57 citations): Life-cycle framework for LLM carbon footprints - identifies 8 main phases
- Tomlinson et al. (2024) in Nature Scientific Reports (43 citations): AI vs human emissions comparison (130-1500x less per page for text, 310-2900x for images)
- Markelius et al. (2024) (38 citations): AI hype "historically unmatched" in planetary costs
- Raiaan et al. (2024) in IEEE Access (488 citations): Documents LLM scaling from millions to trillions of parameters
- Yenduri et al. (2024) in IEEE Access (425 citations): GPT comprehensive review including training procedures and challenges

**Excerpts Created (Training Focus):**
- `/research/ghg/001-jiang-2024-llm-lifecycle-footprint.md` - Life-cycle carbon footprint (8 phases)
- `/research/ghg/002-tomlinson-2024-ai-vs-human-emissions.md` - AI vs human emissions comparison
- `/research/ghg/003-markelius-2024-ai-hype-costs.md` - AI hype planetary costs (critical analysis)
- `/research/ghg/004-raiaan-2024-llm-challenges.md` - LLM scaling and compute trends
- `/research/ghg/005-yenduri-2024-gpt-challenges.md` - GPT technical review with training procedures

**Notes:**
- Limited 2024-2025 papers with specific training emissions NUMBERS (kWh, tCO2e)
- Most papers discuss challenges conceptually without quantifying actual training energy
- Life-cycle assessment approach (Jiang 2024) most comprehensive for training emissions
- Tomlinson comparison focuses primarily on inference/operational emissions, not training
- Foundational training emissions papers (Strubell 2019, Patterson 2021) predate 2024-2025 filter
- Many searches returned general LLM review papers rather than energy-specific research
- OpenAlex academic papers prioritize model capability over environmental analysis
- Note: Some overlap with GHG Inference excerpts (same papers relevant to both topics)

---

### Policy - Current Regulation Landscape for AI Environmental Impact

**OpenAlex Searches Performed:**
1. "AI regulation environmental" - 10 results, general AI papers
2. "data center regulation policy" - 10 results, general papers
3. "EU AI Act environment" - 10 results, general papers
4. "tech emissions disclosure requirements" - 10 results, general tech papers
5. "AI sustainability policy" - 10 results, general health/AI papers
6. "sustainable artificial intelligence carbon footprint" - 10 results, found ecological footprint paper
7. "green AI energy consumption" - 10 results, found green AI review
8. "data center carbon emissions sustainability" - 10 results, general papers
9. "AI governance environmental impact" - 10 results, general papers
10. "machine learning carbon emissions environmental" - 10 results, general papers
11. "digital sustainability disclosure reporting" - 15 results, found ESG reporting papers
12. "corporate carbon disclosure technology" - 15 results, found ESG/climate papers
13. "AI ethics sustainability framework" - 15 results, found AI policy papers
14. "EU AI Act sustainability" - 15 results, general papers
15. "technology company emissions reporting disclosure" - 15 results, found ESG challenges paper
16. "responsible AI governance framework" - 15 results, found AI regulatory papers
17. "AI policy framework government" - 15 results, general AI papers
18. "climate disclosure mandatory regulation" - 15 results, found ESG regulation papers
19. "SEC climate disclosure rule" - 10 results, **FOUND: IMF AI regulation paper, Climate ESG regulation paper**

**Key Findings:**
- Capraro et al. (2024) in PNAS Nexus (205 citations): Interdisciplinary analysis of EU, US, UK AI policy frameworks - environmental impact not central to any major framework
- Comunale (2024) in IMF Working Paper (42 citations): AI regulation differs widely across countries; environmental regulation absent from major policy focus areas
- Oliver Yebenes (2024): CSRD pushing mandatory ESG disclosure in EU; tech companies subject to sustainability reporting
- Chopra et al. (2024) in Sustainability (132 citations): ESG reporting quality concerns; standardization gaps for sustainability metrics
- Martinsson et al. (2024) in Review of Financial Studies (79 citations): Swedish carbon tax evidence shows ~30% emission reduction effectiveness

**Excerpts Created:**
- `/research/policy/001-capraro-2024-genai-policy-inequalities.md`
- `/research/policy/002-comunale-2024-imf-ai-regulation-review.md`
- `/research/policy/003-oliver-2024-esg-climate-regulation.md`
- `/research/policy/004-chopra-2024-esg-reporting-challenges.md`
- `/research/policy/005-martinsson-2024-carbon-pricing-effects.md`

**Notes:**
- Major gap: No dedicated AI environmental impact regulations found in academic literature
- EU AI Act focuses on safety, privacy, bias - not environmental sustainability
- US approach fragmented without federal comprehensive AI environmental law
- ESG/CSRD frameworks could capture AI environmental impacts but not AI-specific
- Carbon pricing exists (Sweden, EU ETS) but not specifically targeting AI/data centers
- Academic literature on AI policy focuses on economic/social impacts, not environmental
- SB 1047 (California) and other US state actions too recent for peer-reviewed coverage
- Tech company voluntary disclosures dominate rather than mandatory requirements
- Gap between policy attention (safety, privacy) and environmental concerns (energy, water, carbon)

---

### Frugal AI - When NOT to Use AI (Continued Research)

**OpenAlex Searches Performed:**
1. "AI overuse unnecessary machine learning" - 10 results, found AI hype papers
2. "simple models vs deep learning" - 10 results, found foundation model papers
3. "when not to use AI" - 10 results, found over-reliance systematic review
4. "traditional algorithms vs neural networks" - 10 results, found healthcare AI papers
5. "AI hype overclaiming" - 2 results, limited direct hits
6. "linear regression vs neural network comparison" - 10 results, found TabPFN paper, TRIPOD+AI
7. "model complexity appropriate machine learning" - 10 results, general papers
8. "tabular data simple models deep learning" - 10 results, found TabPFN paper
9. "XGBoost deep learning comparison benchmark" - 10 results, confirmed gradient boosting dominance
10. "tree boosting neural network tabular" - 10 results, confirmed tree-based method superiority

**Key Findings:**
- Markelius et al. (2024): AI hype is "historically unmatched" - overuse driven by FOMO, fake experts, anthropomorphism
- Humphreys et al. (2024): AI hype creates cybersecurity risks - over-reliance and over-trust as distinct ethical problems
- Zhai et al. (2024): Over-reliance on AI degrades cognitive abilities - 578 citations, systematic review
- Hollmann et al. (2025) in Nature: Gradient-boosted trees dominated tabular data for 20 years; deep learning hasn't changed this
- Collins et al. (2024) in BMJ: TRIPOD+AI guideline treats regression and ML as equivalent - choice should be task-based, not hype-driven

**Excerpts Created:**
- `/research/frugal/007-markelius-2024-ai-hype-planetary-costs.md` - AI hype mechanisms and when NOT to use AI
- `/research/frugal/008-humphreys-2024-ai-hype-cyber-risk.md` - AI hype as cybersecurity risk, over-reliance dangers
- `/research/frugal/009-zhai-2024-ai-overreliance-cognitive.md` - AI over-reliance degrading cognitive abilities
- `/research/frugal/010-hollmann-2025-tabpfn-tabular-data.md` - Gradient boosting still beats deep learning on tabular data
- `/research/frugal/011-collins-2024-tripod-ai-reporting.md` - TRIPOD+AI: when regression is equivalent to ML

**Notes:**
- Strong academic literature on WHY AI gets overused (hype mechanisms)
- Over-reliance and over-trust identified as distinct problems
- Tabular data is key domain where simple methods (XGBoost) consistently beat neural networks
- Clinical prediction guidelines explicitly treat regression as equivalent to AI/ML
- Gap: Limited papers quantifying carbon cost of unnecessary AI adoption
- Gap: Few direct comparisons of energy consumption between traditional and AI methods for equivalent tasks
- Key insight: The term "AI" is being misappropriated to systems that don't warrant it

---

### Frugal AI / Efficient Architectures Research

**OpenAlex Searches Performed:**
1. "green AI efficient machine learning" - 10 results, general papers
2. "small language models efficiency" - 10 results, medical/LLM reviews
3. "model compression energy" - 10 results, general papers
4. "frugal AI sustainable" - 10 results, found TinyML survey
5. "carbon-aware computing AI" - 10 results, general LLM papers
6. "model distillation environmental" - 10 results, general papers
7. "energy efficient neural network training" - 10 results, general papers
8. "sustainable artificial intelligence carbon footprint" - 10 results, **FOUND: AI ecological footprints paper**
9. "TinyML edge computing efficiency" - 10 results, **FOUND: TinyML survey**
10. "knowledge distillation efficient models" - 10 results, general papers
11. "quantization pruning deep learning" - 10 results, **FOUND: FlightLLM FPGA paper**
12. "mixture of experts sparse models" - 10 results, general papers
13. "FlightLLM FPGA inference" - 5 results, **FOUND: FlightLLM paper details**
14. "Tiny Machine Learning survey" - 5 results, **FOUND: TinyML comprehensive survey**
15. "AI ecological footprint carbon emissions" - 10 results, **FOUND: Wang 2024 67 countries**
16. "memristor neural network energy efficient" - 5 results, **FOUND: Memristor neuromorphic chips**

**Key Findings:**
- Barbierato & Gatti (2024): "Red AI" vs "Green AI" framework - fundamental tension between performance and sustainability
- Capogrosso et al. (2024): TinyML comprehensive survey - ML on milliwatt-scale edge devices
- Zeng et al. (2024): FlightLLM achieves 6x energy efficiency improvement over GPUs using FPGAs
- Duan et al. (2024): Memristor-based neuromorphic chips as paradigm shift for energy-efficient AI
- Wang et al. (2024): AI reduces ecological footprints in 67 countries, but context matters (industrial sector, trade openness)
- Weilenmann et al. (2024): Single memristor emulates multiple synaptic mechanisms for efficient neural networks

**Excerpts Created:**
- `/research/frugal/001-barbierato-2024-green-ai-survey.md` - Red AI vs Green AI framework
- `/research/frugal/002-capogrosso-2024-tinyml-survey.md` - TinyML comprehensive survey
- `/research/frugal/003-zeng-2024-flightllm-fpga.md` - FPGA-based efficient LLM inference
- `/research/frugal/004-duan-2024-memristor-neuromorphic.md` - Memristor neuromorphic chips
- `/research/frugal/005-wang-2024-ai-ecological-transitions.md` - AI impact on ecological footprints (67 countries)
- `/research/frugal/006-weilenmann-2024-memristor-synaptic.md` - Single memristor multiple synaptic mechanisms

**Notes:**
- Three main approaches to frugal AI: (1) Algorithmic (TinyML, compression), (2) Hardware (FPGA, memristors), (3) Systemic (policy, deployment context)
- FlightLLM demonstrates that specialized hardware can dramatically outperform GPUs for energy efficiency
- Neuromorphic computing (memristors) represents paradigm shift from von Neumann architecture
- Macro-level studies (Wang 2024) show AI can reduce emissions overall, but industrial context matters
- Gap: Limited papers on carbon-aware scheduling and workload shifting
- Gap: Few papers comparing small language models (SLMs) to LLMs on equivalent tasks
- TinyML enables edge inference, eliminating data transmission energy costs
- Hardware-software co-design is emerging as key strategy for sustainable AI

---

### Water Consumption - Claims Scrutiny (Water Positive Pledges)

**OpenAlex Searches Performed:**
1. "water positive corporate claims" - 10 results, general environmental papers
2. "water stewardship data center" - 10 results, unrelated medical/health papers
3. "water offset criticism" - 10 results, limited direct relevance
4. "bluewashing water claims" - 10 results, found greenwashing/capitalism paper
5. "corporate water neutrality" - 10 results, general sustainability papers
6. "data center water consumption AI" - 10 results, general AI papers
7. "corporate water replenishment offset" - 10 results, found CSR water supply paper
8. "water footprint technology companies" - 10 results, general papers
9. "greenwashing ESG reporting verification" - 10 results, found ESG challenges paper
10. "cloud computing environmental impact water" - 10 results, limited relevance
11. "microsoft google water positive" - 10 results, general papers
12. "translating earth system boundaries cities businesses" - 5 results, **FOUND: Bai et al. 2024**
13. "greenwashing ESG" - 10 results, **FOUND: Zhang 2024, Long et al. 2024**
14. "sustainability pledges commitments verification" - 10 results, **FOUND: low-quality offsets paper**
15. "net zero corporate claims verification" - 10 results, found offset quality issues

**Key Findings:**
- Trencher et al. (2024) in Nature Communications: Major companies purchase low-quality carbon offsets - methodology applicable to water claims
- Chopra et al. (2024): ESG reporting lacks standardization, verification - same gaps apply to water disclosure
- Bai et al. (2024) in Nature Sustainability: Earth system boundaries framework exposes gap between corporate claims and watershed impacts
- de Freitas Netto et al. (2024): Critical theory of greenwashing as systemic feature of green capitalism
- Silva Rodriguez (2024): CSR water supply review identifies gaps in corporate water accountability

**Excerpts Created:**
- `/research/water/007-trencher-2024-offset-quality-implications.md` - Low-quality offsets as analogy for water claims
- `/research/water/008-chopra-2024-esg-reporting-challenges.md` - ESG verification gaps
- `/research/water/009-bai-2024-earth-system-boundaries.md` - Planetary boundaries vs corporate accounting
- `/research/water/010-freitas-netto-2024-greenwashing-capitalism.md` - Critical theory of greenwashing
- `/research/water/011-silva-2024-csr-water-supply.md` - CSR water stewardship gaps

**Notes:**
- Limited direct academic papers on "water positive" claims by tech companies specifically
- Carbon offset criticism literature provides strong analogy for water offset scrutiny
- ESG reporting challenges papers reveal systemic verification gaps
- Greenwashing theory provides framework for skeptical analysis
- Key issues identified: watershed-specific impacts vs global aggregates, temporal mismatches, third-party verification gaps
- Gap: No peer-reviewed assessment of Microsoft/Google/Meta water positive pledge methodologies
- Gap: Academic papers on water credit quality standards and verification lacking

---

### Data Center Growth and Infrastructure Expansion Research

**OpenAlex Searches Performed:**
1. "data center growth projections" - 10 results, mostly unrelated (event-study designs, MRI, etc.)
2. "AI infrastructure expansion" - 10 results, general AI papers
3. "hyperscale data center construction" - 10 results, found PUE paper, China computing project paper
4. "data center electricity demand forecast" - 10 results, general energy papers
5. "AI compute demand growth" - 10 results, general AI papers
6. "data center energy consumption" - 15 results, general papers
7. "AI energy consumption training" - 15 results, general AI papers
8. "electricity demand artificial intelligence" - 15 results, general papers
9. "datacenter power grid" - 15 results, found GaN/SiC power devices paper
10. "computing carbon footprint" - 15 results, found MEGA12 green computing paper
11. "AI sustainability environmental impact" - 15 results, general papers
12. "sustainable data center" - 20 results, general sustainability papers
13. "power usage effectiveness PUE" - 20 results, **FOUND: Data center cooling review, PUE tool paper**
14. "GPU energy machine learning" - 20 results, general ML papers
15. "large language model energy carbon" - 15 results, general LLM papers
16. "generative AI energy consumption" - 15 results, general papers
17. "cloud computing sustainability" - 15 results, general cloud papers
18. "ChatGPT energy carbon emissions" - 15 results, **FOUND: Jiang et al. 2024 LLM lifecycle paper**
19. "global data center electricity consumption" - 15 results, general papers
20. "IEA data center electricity" - 10 results, general papers
21. "hyperscale cloud infrastructure" - 10 results, **FOUND: AI hype paper, Compute North vs South**
22. "data center waste heat recovery" - 10 results, general papers
23. "immersion cooling data center" - 10 results, **FOUND: Immersion cooling study, chip-scale thermal management**
24. "AI water consumption" - 15 results, general papers
25. "renewable energy data center" - 15 results, general papers

**Key Findings:**
- Li et al. (2025): "Making AI Less Thirsty" - projects 4.2-6.6 billion cubic meters AI water demand by 2027 (31 citations)
- Jiang et al. (2024): LLM lifecycle carbon footprint warning - 8 phases of emissions, "feverish" industry development (57 citations)
- Xie et al. (2024): China's EWCRT Project - 8 hubs, 10 clusters, potential 2125-9500 Mt CO2 reduction by 2050 (14 citations)
- Mohammed et al. (2024): Data center cooling critical review - 95% of cooling load from IT equipment (81 citations)
- Commins & Irion (2025): EU policy for "planet proof computing" by 2030 - reporting to become binding targets (3 citations)

**Excerpts Created:**
- `/research/datacenters/007-li-2025-ai-water-growth-projections.md` - AI water demand projections to 2027
- `/research/datacenters/008-jiang-2024-llm-lifecycle-infrastructure.md` - LLM lifecycle carbon footprint warning
- `/research/datacenters/009-xie-2024-china-ewcrt-infrastructure.md` - China's East-West Computing Resources Transmission Project
- `/research/datacenters/010-mohammed-2024-dc-cooling-energy-review.md` - Data center cooling critical review
- `/research/datacenters/011-commins-2025-eu-dc-sustainability-policy.md` - EU data center sustainability policy

**Notes:**
- OpenAlex academic literature on data center GROWTH specifically is limited
- Most papers focus on efficiency/sustainability rather than expansion rates
- Gap: Limited peer-reviewed papers with specific MW or GW capacity projections
- Gap: Few academic papers tracking new construction pipeline or geographic distribution
- Gap: Investment trends (billions in DC investment) mainly in industry reports, not academic literature
- Gap: AI-specific vs general data center growth differentiation underdeveloped
- China's EWCRT is unique case study of coordinated national infrastructure planning
- EU policy paper provides regulatory perspective on containing data center growth
- Li et al. water projections provide quantified growth implications

---

### Policy - Proposed Regulation for AI Environmental Impact

**OpenAlex Searches Performed:**
1. "AI regulation proposed environmental" - 10 results, general LLM/AI papers
2. "data center energy efficiency standards" - 10 results, general papers
3. "mandatory climate disclosure technology" - 10 results, found ESG papers
4. "carbon pricing digital services" - 10 results, general papers
5. "EU energy efficiency directive data center" - 10 results, general papers
6. "EU AI Act sustainability environment" - 15 results, general AI papers
7. "digital sustainability policy regulation" - 15 results, general papers
8. "data center sustainability regulation policy" - 15 results, general papers
9. "California SB AI regulation" - 10 results, limited direct hits
10. "CSRD corporate sustainability reporting directive" - 15 results, **FOUND: Double materiality, BSC framework papers**
11. "energy efficiency directive recast 2023" - 15 results, general building papers
12. "AI governance environmental sustainability" - 15 results, general AI papers
13. "green AI policy framework proposal" - 15 results, general papers
14. "sustainable computing regulation proposal" - 15 results, general papers
15. "SEC climate disclosure rule technology" - 15 results, **FOUND: IMF AI regulation paper**
16. "proposed mandatory AI carbon disclosure" - 10 results, limited direct hits
17. "EU data center sustainability binding targets" - 10 results, general papers
18. "carbon border adjustment digital" - 10 results, general papers
19. "AI transparency energy reporting" - 10 results, general papers
20. "sustainable AI policy recommendation framework" - 15 results, general papers
21. "generative AI regulation sustainability framework" - 15 results, general AI papers
22. "AI Act EU sustainability energy" - 15 results, general AI papers

**Key Findings:**
- Hristov & Searcy (2024) in Management Decision (48 citations): CSRD implementation framework through Sustainability Balanced Scorecard - four-step process for mandatory ESG reporting
- Dragomir et al. (2024) in Accounting in Europe (39 citations): Double materiality disclosure under CSRD 2022/2464 - dual-perspective analysis starting 2024
- Walter (2024) in Discover AI (87 citations): Proposes "dynamic laws" regulatory model for adaptive AI governance
- Capraro et al. (2024) in PNAS Nexus (205 citations): Comparative analysis of EU, US, UK AI policy frameworks - finds no major framework addresses environmental sustainability adequately
- Oliver Yebenes (2024) in Eurasian Economic Review (52 citations): CSRD pushing ESG indicators from voluntary to mandatory

**Excerpts Created:**
- `/research/policy/006-hristov-2024-csrd-balanced-scorecard.md` - CSRD implementation framework
- `/research/policy/007-dragomir-2024-double-materiality-csrd.md` - Double materiality assessment requirements
- `/research/policy/008-walter-2024-dynamic-laws-ai-governance.md` - Proposed adaptive "dynamic laws" model
- `/research/policy/009-capraro-2024-genai-policy-frameworks.md` - EU/US/UK policy framework comparison
- `/research/policy/010-oliver-2024-csrd-esg-regulation.md` - CSRD mandatory ESG disclosure

**Notes:**
- CSRD (Corporate Sustainability Reporting Directive) is the primary binding framework that will capture tech company environmental impacts
- Double materiality requires companies to disclose both environmental impacts AND how sustainability risks affect them financially
- No AI-specific environmental regulation found in academic literature
- EU AI Act focuses on safety, transparency, and human oversight - not environmental sustainability
- The "dynamic laws" concept is proposed to address gap between rapid AI advancement and slow regulatory processes
- Gap: California SB 1047 and other US state-level actions too recent for peer-reviewed coverage
- Gap: EU Energy Efficiency Directive data center provisions not well-covered in academic literature
- Gap: Limited academic analysis of voluntary commitments becoming mandatory
- Key theme: Current AI policy focuses on socioeconomic impacts; environmental regulation relies on general ESG frameworks, not AI-specific rules

---

### GHG Numbers Compilation (Quantitative Carbon/Energy Data)

**OpenAlex Searches Performed:**
1. "GPT carbon footprint tonnes CO2" - 12 results, limited direct hits
2. "LLM training energy kWh MWh" - 13 results, found timeshifting strategies paper
3. "ChatGPT emissions per query" - 15 results, found Reducing Carbon Impact GenAI paper
4. "AI inference energy consumption watts" - 15 results, found TPU v4 paper
5. "machine learning carbon emissions measurement" - 20 results, general papers
6. "large language model carbon footprint training" - 20 results, general LLM papers
7. "generative AI energy carbon emissions" - 20 results, found Green AI systematic review
8. "deep learning environmental impact carbon" - 20 results, general papers
9. "making AI less thirsty water" - 10 results, **FOUND: Li et al. 2023 (138 citations)**
10. "CodeCarbon ML CO2 track" - 10 results, found BERT fine-tuning paper
11. "sustainable AI green machine learning" - 15 results, general papers
12. "Power Hungry Processing Watts generative AI" - 10 results, found GenAI environmental impact paper
13. "Strubell energy emissions NLP training" - 10 results, general papers
14. "image generation AI energy CO2" - 10 results, general papers

**Key Findings (Quantitative Numbers):**
- Li et al. (2023): GPT-3 training = 700,000 liters water; ChatGPT = 500ml per 20-50 queries; 4.2-6.6B m3 AI water by 2027 (138 citations)
- Tomlinson et al. (2024): AI emits 130-1500x less CO2 per page than humans; 310-2900x less per image (43 citations)
- Chien et al. (2023): CarbonMin routing strategy reduces GenAI inference carbon (106 citations)
- Jouppi et al. (2023): TPU v4 uses 2-6x less energy, 20x less CO2e than on-premise DSAs (351 citations)
- Verdecchia et al. (2023): Green AI achieves energy savings up to 115%, >50% common (205 citations)
- Wang et al. (2023): BERT fine-tuning energy varies across tasks/hardware/methods (10 citations)

**Excerpts Created:**
- `/research/ghg/012-li-2023-making-ai-less-thirsty-water-numbers.md` - GPT-3 700K liters water, ChatGPT 500ml per 20-50 queries
- `/research/ghg/013-tomlinson-2024-ai-vs-human-emissions-comparison.md` - AI 130-2900x less CO2 than humans per task
- `/research/ghg/014-chien-2023-genai-inference-carbon-reduction.md` - CarbonMin routing for inference emissions
- `/research/ghg/015-tpu-v4-energy-efficiency-numbers.md` - TPU v4 2-6x less energy, 20x less CO2e
- `/research/ghg/016-verdecchia-2023-green-ai-systematic-review-savings.md` - Green AI savings up to 115%
- `/research/ghg/017-wang-2023-bert-finetuning-energy-carbon.md` - BERT fine-tuning energy study

**Notes:**
- Most quantitative data comes from specific hardware/system measurements rather than standardized methodology
- Water consumption (Li et al.) and efficiency comparisons (TPU v4) provide most concrete numbers
- AI vs human comparison (Tomlinson) includes critical caveat about rebound effects
- Green AI systematic review shows efficiency improvements are achievable (>50% savings common)
- Gap: Limited standardized methodology for measuring per-query emissions across different providers
- Gap: Specific training emissions (kWh, tCO2e) for GPT-4, Claude, Gemini not publicly available
- Most papers note significant variation by location (grid carbon intensity), time (renewable availability), and hardware

---

### Community Impact - Grid/Ratepayer Research

**OpenAlex Searches Performed:**
1. "data center electricity grid strain" - 10 results, general energy papers
2. "AI electricity demand residential rates" - 10 results, general papers
3. "data center grid infrastructure costs" - 10 results, general papers
4. "electricity price data center impact" - 10 results, general papers
5. "power grid reliability data center" - 10 results, general papers
6. "data center electricity consumption growth" - 10 results, general papers
7. "data center energy demand utility" - 10 results, general papers
8. "AI computing power infrastructure" - 10 results, general AI papers
9. "hyperscale data center power" - 10 results, **FOUND: AI hype paper, Green Cloud Continuum, China EWCRT**
10. "data center sustainability environmental impact" - 15 results, general papers
11. "electricity load growth forecast data centers" - 10 results, **FOUND: Modern Computing paper**
12. "generative AI energy consumption" - 10 results, general LLM papers
13. "power demand growth artificial intelligence" - 10 results, general papers
14. "computing sustainability carbon footprint" - 10 results, general papers
15. "IEA data center electricity" - 10 results, general papers
16. "power hungry processing AI training" - 10 results, general papers
17. "smart grid load management data center" - 10 results, general papers
18. "data center power demand forecast" - 10 results, general papers
19. "GPU energy consumption AI" - 10 results, general papers
20. "carbon footprint machine learning training" - 10 results, general papers
21. "sustainable computing environmental AI" - 10 results, general papers
22. "AI environmental impact energy" - 15 results, general papers
23. "utility electricity rate increase demand growth" - 10 results, general papers
24. "grid reliability electricity load increase" - 10 results, general papers
25. "transmission interconnection queue delay" - 10 results, general papers

**Key Findings:**
- Xie et al. (2024): China's EWCRT Project - 8 hubs, 10 clusters, potential 2,125-9,500 Mt CO2 reduction by 2050, illustrates scale of infrastructure planning
- Kim et al. (2024): Data center PUE varies 1.15-1.43 by climate zone - 24% efficiency difference between locations
- Dhiman et al. (2024): "Sustainability of AI" vs "AI for Sustainability" tension - economic dimension underexplored
- Gajdzik et al. (2024): Global energy crisis context - households pushed into poverty while energy demand grew

**Excerpts Created:**
- `/research/community/006-xie-2024-china-computing-transmission.md`
- `/research/community/007-kim-2024-data-center-pue-tool.md`
- `/research/community/008-dhiman-2024-ai-sustainability-tension.md`
- `/research/community/009-gajdzik-2024-energy-crisis-efficiency.md`

**Notes:**
- Limited peer-reviewed papers specifically on data center impacts on residential electricity rates
- Academic literature focuses on data center efficiency (PUE) rather than ratepayer cost distribution
- Gap: Few papers on utility infrastructure cost allocation for data center interconnection
- Gap: Limited academic coverage of specific regional cases (Virginia, Texas, Georgia grid strain)
- Gap: "Who pays" question largely absent from peer-reviewed literature
- China's EWCRT provides only documented case of coordinated national data center grid planning
- Energy crisis papers provide macroeconomic context but don't isolate data center contribution
- PJM/ERCOT load growth projections mainly in industry reports, not academic literature
- Most academic research on grid reliability doesn't specifically address data center loads

---


### Policy - 2025 AI Regulation, Environmental Policy, Tech Sustainability Governance

**OpenAlex Searches Performed:**
1. "AI regulation environmental policy" (2025 filter) - 15 results, mostly healthcare/general AI papers
2. "EU AI Act environment 2025" - 15 results, limited direct relevance
3. "data center regulation policy" - 15 results, general papers
4. "ESG disclosure mandatory 2025" - 15 results, **FOUND: mandatory vs voluntary paper, green procurement paper**
5. "AI sustainability governance technology" - 15 results, general papers
6. "corporate carbon emissions accountability disclosure" - 15 results, **FOUND: Jiang et al. 2025 Nature Climate Change**
7. "digital infrastructure environmental regulation" - 15 results, general papers
8. "mandatory ESG disclosure policy 2025" - 15 results, **FOUND: Triple Bottom Line paper**
9. "AI governance regulation technology policy" - 20 results, **FOUND: Batool et al. 2025 systematic review (59 citations)**
10. "corporate emissions target accountability" - 15 results, confirmed Jiang et al. findings

**Key Findings (2025 Publications Only):**
- Jiang, Kim & Lu (2025) in Nature Climate Change (23 citations): Of 1,041 emissions targets ending 2020, 9% failed, 31% "disappeared" - only 3 got media coverage. No market reaction, no ESG score decline, no shareholder consequences. Rewards for pledges, no penalties for failures.
- Batool, Zowghi & Bano (2025) in AI and Ethics (59 citations): Systematic review of 28 AI governance articles. Environmental sustainability absent from formal governance frameworks. Focus remains on ethical risks (bias, privacy, safety).
- Cui, Li, Xue & Zhang (2025) in J. International Money and Finance (10 citations): Mandatory ESG disclosure has measurably different "real effects" on corporate behavior vs voluntary disclosure.
- Wang & Shen (2025) in J. Environmental Management (10 citations): Green public procurement improves corporate ESG performance - policy mechanism applicable to government AI contracts.

**Excerpts Created:**
- `/research/policy/011-jiang-2025-emissions-target-accountability.md` - Corporate emissions accountability gap
- `/research/policy/012-batool-2025-ai-governance-systematic-review.md` - AI governance excludes environmental concerns
- `/research/policy/013-cui-2025-mandatory-vs-voluntary-esg.md` - Mandatory disclosure effects
- `/research/policy/014-wang-shen-2025-green-procurement-esg.md` - Green procurement as policy mechanism

**Notes:**
- 2025 literature confirms the accountability vacuum for corporate environmental pledges
- AI governance is maturing as a field but systematically ignores environmental impacts
- Mandatory disclosure and green public procurement emerge as promising policy pathways
- No AI-specific environmental regulations found in 2025 academic literature
- Gap: EU Energy Efficiency Directive data center provisions still not well-covered academically
- Gap: California SB 1047 and other US state actions too recent for peer-reviewed analysis
- Key theme: Policy attention on AI safety/privacy, not environmental sustainability

---

### Narrative - Net Impact Analysis Research

**OpenAlex Searches Performed:**
1. "AI net environmental impact" - 10 results, mostly unrelated (ADMET, nanoparticles, image processing)
2. "AI climate benefits vs costs" - 10 results, general healthcare/energy papers
3. "machine learning lifecycle assessment" - 10 results, general LCA papers
4. "AI environmental tradeoffs" - 10 results, general AI papers
5. "digital technology sustainability net effect" - 10 results, general health/disease burden papers
6. "AI sustainability benefits costs tradeoff" - 15 results, general AI papers
7. "artificial intelligence environmental benefit cost analysis" - 15 results, general papers
8. "AI for sustainability vs AI sustainability" - 15 results, healthcare/nanoparticle papers
9. "rebound effect digital technology energy" - 15 results, **FOUND: ICT GHG enablement paper, circular economy paper**
10. "green AI sustainable computing environmental impact" - 15 results, **FOUND: Green sustainable AI thematic paper (81 citations)**
11. "AI carbon footprint climate mitigation" - 15 results, **FOUND: AI digital twin smart cities (143 citations)**
12. "digital technology Jevons paradox rebound" - 15 results, **FOUND: Bieser GHG enablement critique**
13. "ICT digitalization net carbon emissions" - 15 results, **FOUND: Modern computing paper (139 citations)**
14. "AI ecological footprint reduction countries panel" - 10 results, **FOUND: Wang et al. 2024 (174 citations)**
15. "Tomlinson AI emissions human comparison" - 10 results, **FOUND: Tomlinson et al. 2024 (43 citations)**
16. "AI sustainability review" - 10 results, **FOUND: Dhiman et al. 2024 (24 citations)**
17. "Green artificial intelligence initiatives" - 15 results, **FOUND: Alzoubi & Mishra 2024 (112 citations)**
18. "AI climate mitigation decarbonization" - 10 results, **FOUND: Wang et al. 2025 energy transition (128 citations)**

**Key Findings:**
- Wang, Li & Li (2024): Panel data from 67 countries shows AI significantly reduces ecological footprints and carbon emissions, but benefits are context-dependent (industrial composition, trade openness, development level). 174 citations.
- Tomlinson et al. (2024) in Nature Scientific Reports: AI emits 130-1500x less CO2e per page than humans for writing, 310-2900x less per image for illustration. Authors explicitly caveat that rebound effects not included. 43 citations.
- Dhiman et al. (2024): Critical framework distinguishing "Sustainability OF AI" vs "AI FOR Sustainability" - net impact depends on balancing both. Identifies socio-economic dimensions as under-researched.
- Alzoubi & Mishra (2024) in Journal of Cleaner Production: 55 green AI initiatives identified, but most lack empirical validation. "Research discussing these initiatives remains scarce." 112 citations.
- Wang, Li & Li (2025) in Energy Strategy Reviews: Positions AI as "transformative catalyst" for energy transition, but acknowledges scalability and interoperability challenges. 128 citations.
- Raman et al. (2024): Three major Green AI research themes identified (algorithmic efficiency, hardware innovations, carbon footprinting). Major gap: socio-economic dimensions ignored.

**Excerpts Created:**
- `/research/narrative/007-wang-2024-ai-ecological-footprints-67-countries.md` - Macro-level empirical study of AI net positive impact (with critical caveats)
- `/research/narrative/008-tomlinson-2024-ai-vs-human-emissions-comparison.md` - Per-task emissions comparison (with rebound effect caveat)
- `/research/narrative/009-dhiman-2024-sustainability-of-ai-vs-ai-for-sustainability.md` - Framework for net impact analysis
- `/research/narrative/010-alzoubi-2024-green-ai-initiatives-validation-gap.md` - 55 initiatives lack empirical validation
- `/research/narrative/011-wang-2025-ai-energy-transition-catalyst.md` - AI as catalyst with opportunity cost question
- `/research/narrative/012-raman-2024-green-sustainable-ai-thematic-analysis.md` - Three themes, one major gap (socio-economic)

**Key Net Impact Insights:**
1. **Macro studies show AI can be net positive** - Wang et al. (2024) finds significant ecological footprint reduction across 67 countries
2. **Per-task studies show AI is more efficient** - Tomlinson et al. (2024) finds 130-2900x less emissions per output
3. **BUT rebound effects are systematically ignored** - Every paper acknowledging benefits also caveats that rebound effects not studied
4. **55 "green AI" initiatives lack validation** - Claims of sustainable AI not backed by empirical evidence
5. **Socio-economic dimensions neglected** - WHO bears costs vs WHO gets benefits is not being studied
6. **Opportunity cost unasked** - Could AI investment dollars deliver more climate benefit elsewhere?

**Net Impact Formula (Dhiman Framework):**
NET = (Benefits from "AI FOR Sustainability") - (Costs from "Sustainability OF AI") - (Rebound Effects) - (Opportunity Costs)

Current literature measures first two terms imperfectly; largely ignores last two.

**Notes:**
- No paper found that comprehensively quantifies net impact including all four terms
- Macro-level positive findings may reflect correlation (wealthy countries do both AI and sustainability) rather than causation
- The "AI vs human" comparison (Tomlinson) is provocative but narrow framing
- Gap: Rebound effects from AI efficiency gains at societal scale
- Gap: Opportunity cost analysis of AI infrastructure investment
- Gap: Environmental justice - who bears data center impacts?
- Key theme: Benefits are theoretical/projected, costs are measured/current

---

### Community Impact - 2025 Data Center Grid/Community Research

**OpenAlex Searches Performed:**
1. "data center electricity grid community" (2025) - 15 results, found Li et al. water paper (31 citations)
2. "AI infrastructure local impact" (2025) - 15 results, mostly healthcare/education papers
3. "data center environmental justice" (2025) - 15 results, limited direct relevance
4. "data center power demand grid reliability" (2025) - 15 results, battery/cybersecurity papers
5. "hyperscale data center energy growth" (2025) - 15 results, found Planet Proof Computing paper
6. "AI electricity demand energy consumption" (2025) - 15 results, found G-20 tech innovation paper
7. "generative AI carbon footprint environmental" (2025) - 15 results, limited direct hits
8. "sustainable computing infrastructure environmental impact" (2025) - 15 results, general papers
9. "AI computational resources environmental sustainability" (2025) - 15 results, general papers
10. "electricity load growth artificial intelligence demand" (2025) - 15 results, general papers
11. "computing waste sustainability academic" (2025) - 15 results, **FOUND: Lord et al. HPC waste paper**
12. "large language model energy carbon environmental" (2025) - 20 results, general papers
13. "AI sustainable higher education ethics efficiency" (2025) - 10 results, **FOUND: Khan et al. paper**
14. "digital infrastructure sustainability carbon energy" (2025) - 15 results, general papers
15. "cloud computing carbon footprint sustainability energy" (2025) - 15 results, general papers
16. "AI digital economy carbon emissions" (2025) - 15 results, general papers
17. "digital sustainability environmental governance policy" (2025) - 15 results, general papers

**Key Findings (2025 Publications Only):**
- Lord et al. (2025) in CHI Conference: Academic/research institutions "reinforce and embed, rather than challenge, expectations of growth and waste" in HPC - generative AI and larger models "multiplying" demand
- Achuthan et al. (2025) in Discover Sustainability: Cybersecurity demands resource-intensive computing, creating fundamental tension with sustainability for data centers
- Khan et al. (2025) in Discover Sustainability: University AI deployment creates institutional infrastructure demands - addresses digital divide and equity concerns

**Excerpts Created:**
- `/research/community/013-lord-2025-hpc-computing-waste-growth.md` - Academic computing waste and growth culture
- `/research/community/014-achuthan-2025-cybersecurity-sustainability-integration.md` - Cybersecurity vs sustainability tension
- `/research/community/015-khan-2025-ai-sustainable-higher-education.md` - University AI infrastructure demands

**Notes:**
- Limited 2025 peer-reviewed papers specifically on local community impacts of data centers
- Most papers focus on efficiency/sustainability frameworks rather than community-level impacts
- Gap: Electricity rate impacts on residential customers from data center demand still underdocumented
- Gap: Environmental justice dimension (who bears data center costs vs benefits) largely absent from 2025 literature
- Gap: Specific regional case studies (Virginia, Texas, Georgia grid strain) remain in news media, not academic literature
- Key finding: Academic/research computing is a significant and growing demand driver with cultural barriers to reduction
- The cybersecurity-sustainability tension reveals an inherent conflict: more security = more computing = more energy

---

### Frugal AI - Efficient AI and Green Machine Learning (2025 Papers)

**OpenAlex Searches Performed:**
1. "efficient AI green machine learning" (2025 filter) - 15 results, mostly unrelated (plant disease, food safety)
2. "small language models" (2025 filter) - 15 results, found DeepSeek-R1 (141 citations), TabPFN (307 citations)
3. "model compression efficiency" (2025 filter) - 15 results, found TabPFN again
4. "sustainable AI computing" (2025 filter) - 15 results, general papers
5. "energy efficient deep learning" (2025 filter) - 15 results, **FOUND: photonic accelerator (79 citations), DeepSeek-R1**
6. "LLM efficiency inference" (2025 filter) - 15 results, **FOUND: DynamoLLM (26 citations), Making AI Less Thirsty (31 citations)**
7. "carbon footprint machine learning" (2025 filter) - 15 results, general papers
8. "quantization pruning neural network" (2025 filter) - 15 results, **FOUND: TabPFN, edge deep learning survey**
9. "neuromorphic computing energy" (2025 filter) - 15 results, **FOUND: photonic accelerator, synaptic silicon transistor (45 citations), memristor development (31 citations)**
10. "edge AI inference efficiency" (2025 filter) - 15 results, general papers
11. "spiking neural network energy efficient" (2025 filter) - 15 results, general papers
12. "AI environmental impact energy consumption" (2025 filter) - 15 results, general papers
13. "DeepSeek efficient" (2025 filter) - 10 results, **FOUND: DeepSeek-V3 insights (10 citations)**
14. "knowledge distillation large language model" (2025 filter) - 15 results, general surveys
15. "speculative decoding LLM efficient" (2025 filter) - 10 results, **FOUND: hardware accelerators survey (13 citations), LLM environmental impacts paper**
16. "green AI sustainability" (2025 filter) - 15 results, mostly unrelated

**Key Findings (2025 Publications Only):**
- Stojkovic et al. (2025) at HPCA: DynamoLLM - Energy-efficient LLM inference cluster design from Microsoft Research/UIUC (26 citations)
- Hua, Shen et al. (2025) in Nature: Large-scale photonic accelerator with 16,000+ components, 1 GHz, 3 ns latency (79 citations)
- Pazos, Lanza et al. (2025) in Nature: Standard silicon transistor exhibits neural/synaptic behaviors - 2-transistor cell vs 24+ in current designs (45 citations)
- Lee et al. (2025) in Advanced Materials: Reconfigurable memristors for low-power neuromorphic systems (31 citations)
- Kachris (2025) in Applied Sciences: Survey of hardware accelerators for LLMs covering GPUs, FPGAs, custom architectures with energy focus (13 citations)

**Excerpts Created:**
- `/research/frugal/012-stojkovic-2025-dynamollm-energy-efficient-inference.md` - DynamoLLM for production-scale energy savings
- `/research/frugal/013-hua-2025-photonic-accelerator-ultralow-latency.md` - Photonic computing at scale (Nature)
- `/research/frugal/014-pazos-2025-silicon-transistor-neuromorphic.md` - 2-transistor neuromorphic cell (Nature)
- `/research/frugal/015-lee-2025-memristor-low-power-neuromorphic.md` - Memristor review for neuromorphic systems
- `/research/frugal/016-kachris-2025-hardware-accelerators-llm-survey.md` - LLM hardware accelerator survey

**Key Themes from 2025 Literature:**
1. **LLM Inference Efficiency** - Focus shifting from training to inference optimization (DynamoLLM)
2. **Alternative Computing Paradigms** - Photonics and neuromorphic approaches maturing rapidly
3. **Standard CMOS Innovation** - Significant efficiency gains possible without exotic materials (silicon transistor paper)
4. **Hardware-Software Co-Design** - Emerging as key strategy (DeepSeek-V3 architecture insights)

**Notes:**
- 2025 literature shows hardware efficiency research maturing beyond benchmarks to production systems
- Nature published two major neuromorphic/photonic papers in early 2025 - indicates field significance
- Limited papers on algorithmic efficiency (small language models, model compression) with high citations in 2025 so far
- Gap: Direct energy/carbon measurements of new hardware approaches vs GPUs not well-documented
- Gap: Production deployment data for photonic and neuromorphic systems still limited
- Most 2025 papers focus on feasibility demonstration rather than environmental impact quantification

---

### Water Consumption - 2025 Papers on AI/Data Center Water (Targeted Search)

**OpenAlex Searches Performed:**
1. "data center water cooling efficiency" (2025 filter) - 15 results, mostly unrelated (solar cells, batteries)
2. "AI infrastructure water" (2025 filter) - 15 results, mostly agriculture/food papers
3. "evaporative cooling data center" (2025 filter) - 15 results, mostly unrelated
4. "data center water consumption" (2025 filter) - 15 results, general chemistry papers
5. "AI water footprint" (2025 filter) - 15 results, **FOUND: Li et al. 2025 CACM (31 citations)**
6. "liquid cooling server data center" (2025 filter) - 15 results, **FOUND: Li & Zhu 2025 (13 citations), Kim et al. 2025 immersion (17 citations)**
7. "WUE water usage effectiveness data center" (2025 filter) - 15 results, **FOUND: Lei et al. 2025 (3 citations)**
8. "ChatGPT environmental sustainability carbon water" (2025 filter) - 15 results, **FOUND: Berthelot et al. 2025 (10 citations)**
9. "LLM sustainability carbon water" (2025 filter) - 15 results, **FOUND: "Efficiency Is Not Enough" Wright et al. (6 citations)**
10. "immersion cooling data center server" (2025 filter) - 15 results, confirmed Kim et al. 2025

**Key 2025 Findings:**
- Wright et al. (2025) CACM: "Efficiency Is Not Enough" - efficiency gains overwhelmed by demand growth (Jevons paradox)
- Berthelot et al. (2025) CACM: GenAI services environmental impact - inference now dominates operational footprint
- Li & Zhu et al. (2025) Energies: Liquid cooling review - chip power density makes water-based cooling necessary
- Kim et al. (2025) Applied Thermal Eng: Immersion cooling - potential waterless DC cooling solution (17 citations)
- Lei et al. (2025) Energy & Buildings: US small/midsize DCs more water-intensive despite energy efficiency gains

**Papers Already Documented (not duplicated):**
- 017: Google Gemini water measurements (Elsworth 2025)
- 018: Li et al. 2025 CACM - AI water projections
- 022: Lei et al. 2025 - US midsize data centers WUE

**New Excerpts Created:**
- `/research/water/023-wright-2025-efficiency-not-enough-sustainable-ai.md` - Jevons paradox in AI sustainability
- `/research/water/024-berthelot-2025-genai-environmental-impact-services.md` - GenAI infrastructure environmental analysis
- `/research/water/025-li-zhu-2025-data-center-liquid-cooling-review.md` - Technical necessity of liquid cooling
- `/research/water/026-kim-2025-immersion-cooling-high-density-servers.md` - Waterless cooling alternative

**Key 2025 Research Themes Identified:**
1. Efficiency paradox: Better WUE doesn't mean less total water if AI demand grows faster
2. Inference dominance: Serving billions of queries now exceeds training water footprint
3. Technical lock-in: AI chip power density physically requires liquid (water-based) cooling
4. Emerging solutions: Immersion cooling offers waterless path but limited deployment
5. Hidden burden: 40% of servers in small/midsize DCs with worse WUE than hyperscale

**Notes:**
- 2025 CACM published three related papers: Li et al., Wright et al., Berthelot et al. - signals academic establishment concern
- Limited 2025 papers with specific new water consumption NUMBERS - most cite Li et al. 2023/2025
- Immersion cooling (Kim 2025) is main technical alternative to evaporative cooling
- No 2025 papers found specifically assessing corporate "water positive" pledge methodologies
- Gap persists: Independent verification of Google's 0.26 mL/prompt claim

---

