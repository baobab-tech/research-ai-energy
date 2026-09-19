# The EU's only mandatory data-centre reporting regime collects facility-level energy and water data and then keeps it confidential

**Topic:** Policy and regulation — the design of the EU data-centre disclosure obligation
**Source:** Directive (EU) 2023/1791 Article 12; Commission Delegated Regulation (EU) 2024/1364
**Type:** primary legal text
**URL:** https://eur-lex.europa.eu/eli/reg_del/2024/1364/oj
**Source note:** EED: https://eur-lex.europa.eu/eli/dir/2023/1791/oj
**Published:** 2024-03-14 (DR adopted); OJ 2024-05-16

## Finding

Article 12 of the recast Energy Efficiency Directive requires member states to make owners and operators of data centres with installed IT power demand of at least 500 kW publish energy performance information; Delegated Regulation (EU) 2024/1364 sets the indicators and creates the European database on data centres. The regime collects facility-level data — total energy consumption, IT equipment energy, installed IT power demand, water input under EN 50600-4-9, waste heat reused and its temperature, renewable energy split by Guarantee of Origin, PPA and on-site generation, floor areas, redundancy levels and grid-support capability — and then publishes it only in aggregate. Article 5(5) directs that individual data centre information "shall be kept confidential" as commercial and trade secrets, and Annex IV suppresses any breakdown with fewer than three reporting facilities.

## Key Data

| Element | Provision | Value |
|---|---|---|
| Scope threshold | Art. 1 | Installed IT power demand ≥ 500 kW |
| First report | Art. 3(1) | By 15 September 2024, covering calendar year 2023 |
| Annual report thereafter | Art. 3(1) | By 15 May, covering the preceding calendar year |
| First-period exemptions | Art. 3(2) | Certain metrics may be omitted with justification; colocation operators get two periods |
| Publication | Art. 5(2), Annex IV | EU and member-state aggregates only |
| Confidentiality | Art. 5(5) | Facility-level data withheld under Reg. 1049/2001 and Dir. 2003/4/EC |
| Aggregation rule | Annex IV | Weighted by total energy consumption; suppressed below 3 reporting facilities |
| Stricter national thresholds | — | Germany's EnEfG (2023) extends reporting to ≥ 300 kW |

## Methodology

Reading of the delegated regulation. The 500 kW threshold is installed IT power demand, not facility connection capacity, so a hyperscale campus and a 500 kW enterprise room sit in the same population with no size-weighted disclosure.

## Limitations and conflicts

The confidentiality rule is the structural limit: no outside party can verify a named operator's PUE, water draw or renewable claim from this regime, which leaves corporate self-reporting as the only source of facility-level numbers. Water reporting is confined to EN 50600-4-9 categories 1 and 2 — direct potable and non-potable input — and excludes indirect water consumed by upstream power generation, which is the larger term for most grid-connected sites. The scheme records renewable energy including Guarantees of Origin, so a high renewable factor can be met by unbundled certificate purchase rather than by physical supply. There is no AI or compute-workload dimension at all: the regime cannot distinguish AI training capacity from conventional hosting.

## Relation to existing corpus

No direct overlap — the repo held nothing on the EED or the European database. Results from the first round are in 020.

---
Retrieved: 2026-09-19
Search: WebSearch "Energy Efficiency Directive Article 12 data centre reporting delegated regulation 2024/1364"; EUR-Lex OJ text
