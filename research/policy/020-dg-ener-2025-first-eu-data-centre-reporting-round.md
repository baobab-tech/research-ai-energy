# The first EU data-centre reporting round captured 36% of facilities, six member states reported nothing, and the weighted average PUE was 1.36

**Topic:** Policy and regulation — what the EU's mandatory data-centre disclosure actually produced
**Source:** European Commission DG ENER (study by EY Belgium, Borderstep Institute, AIT), "Assessment of the energy performance and sustainability of data centres in EU — First technical report"
**Type:** agency report
**URL:** https://op.europa.eu/en/publication-detail/-/publication/83be4c3e-5c79-11f0-a9d0-01aa75ed71a1
**Published:** 2025-07 (manuscript completed June 2025); ISBN 978-92-68-29508-3, doi:10.2833/3168794

## Finding

770 data centres reported under the first round of the European database, which the authors put at 36% of the EU population estimated from datacentermap.com, and they note the ratio of reported to actual installed capacity or energy is probably lower still because large facilities are under-represented. Six member states returned no data at all (Cyprus, Czechia, Estonia, Romania, Slovakia, Slovenia) and five others returned fewer than three facilities. Reporting concentrated in Germany (335 of an estimated 456, 73%) and France (133 of 264, 50%); Ireland, where data centres take roughly a fifth of national electricity, returned 18 of an estimated 123 (15%). Reported facilities consumed 14,088 GWh against 3,738.86 MW of installed IT power demand and drew 6,223,391 m³ of water.

## Key Data

| Metric | Value | Boundary / method |
|---|---|---|
| Reporting facilities | 770 | First reporting period, data as of 20 June 2025 |
| Coverage | 36% of estimated EU data centres | Denominator from datacentermap.com; capacity coverage likely lower |
| Member states with zero reports | 6 (CY, CZ, EE, RO, SK, SL) | — |
| Total reported energy | 14,088 GWh | Reporting facilities only |
| Total reported IT power demand | 3,738.86 MW | Installed |
| Total reported water input | 6,223,391 m³ | EN 50600-4-9 categories 1 and 2; excludes indirect/upstream water |
| Average PUE | 1.36 | Weighted by total energy consumption, n=681 |
| PUE by size | 1.63 (100–500 kW), 1.64 (500 kW–1 MW), 1.55 (1–2 MW), 1.47 (2–10 MW), 1.21 (>10 MW) | Same weighting |
| PUE by type | 1.43 colocation, 1.24 co-hosting, 1.31 enterprise | — |
| Average WUE | 0.58 m³/MWh | Weighted, n=458 (only facilities reporting non-zero water and IT energy) |
| WUE by size | 0.193, 0.561, 0.413, 0.499, 0.705 m³/MWh across the five size bands | — |
| Renewable Energy Factor | 0.87 EU weighted average | Against 45.3% renewables in EU gross electricity consumption |
| Data judged reliable | ~70% of participants | Consistency across reported metrics |

## Methodology

Aggregation of operator-submitted returns to the European database under Delegated Regulation (EU) 2024/1364, anonymised before release to the study team, which received only prioritised indicators. PUE, WUE, ERF and REF are computed by the study team from reported raw quantities and weighted by total energy consumption. The coverage ratio is an estimate against a commercial facility directory, not a census. The report flags two specific figures as unreliable: back-up generator energy ("significantly misaligned with reality" on interview validation) and renewable energy from PPAs, where the mean is 5,322,448 kWh against a median of 0, attributed to outliers or unit misinterpretation.

## Limitations and conflicts

The authors are consultants (EY Belgium) and research institutes (Borderstep, AIT) under contract to DG ENER; the report carries the standard disclaimer that it does not represent the Commission's position. The 0.87 renewable energy factor is inflated by Guarantees of Origin, which the scheme counts without additionality; it is roughly twice the EU grid average and should not be read as physical renewable supply. WUE covers only 458 facilities that reported non-zero water, biasing the average toward water-cooled sites while the non-reporters are unknown. The size-band PUE trend — larger facilities cleaner — is partly a selection artefact below the 500 kW mandatory threshold, where the authors say reporting is voluntary and skews to ambitious operators. Nothing in the dataset identifies AI or accelerated-compute workloads.

## Relation to existing corpus

First mandatory-regime measurement in the corpus. The 1.36 weighted average PUE sits below the Uptime Institute global self-reported figure of ~1.58 cited in the same report, and the gap is worth treating as a coverage effect rather than an EU efficiency advantage. Complements 019. No direct overlap with existing policy excerpts.

---
Retrieved: 2026-09-19
Search: WebSearch "European database data centres JRC first reporting round results"; PDF retrieved from op.europa.eu and text-extracted locally
