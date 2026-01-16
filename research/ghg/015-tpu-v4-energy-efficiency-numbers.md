# TPU v4: 2-6x Less Energy, 20x Less CO2e Than On-Premise DSAs

**Topic:** GHG Emissions - Numbers Compilation
**Source:** Jouppi et al. (Google), 2023
**URL:** https://doi.org/10.1145/3579371.3589350

## Key Numbers

| Metric | Value | Context |
|--------|-------|---------|
| Performance vs TPU v3 | 2.1x faster | Per-chip performance improvement |
| Performance/Watt vs TPU v3 | 2.7x improvement | Energy efficiency gain |
| System size | 4096 chips | TPU v4 supercomputer scale |
| Overall speedup | ~10x faster | Compared to v3 (4x size + 2.1x per-chip) |
| Training utilization | ~60% of peak FLOPS | Average for large language models |
| vs Graphcore IPU Bow | 4.3-4.5x faster | Similar-sized systems comparison |
| vs Nvidia A100 | 1.2-1.7x faster | Performance comparison |
| Power vs Nvidia A100 | 1.3-1.9x less | Energy consumption comparison |
| Energy vs on-premise DSAs | 2-6x less | Google Cloud vs typical data centers |
| CO2e vs on-premise DSAs | ~20x less | Carbon emissions comparison |
| OCS cost share | <5% | Optical circuit switches as % of system cost |
| OCS power share | <3% | Optical circuit switches as % of system power |
| SparseCores speedup | 5-7x | For embedding-heavy models |
| SparseCores die area | 5% | Minimal silicon overhead |

## Methodology Notes

- Direct measurements from production TPU v4 systems deployed since 2020
- Comparisons performed on similar-sized systems for fair assessment
- Energy-optimized warehouse-scale computers (Google Cloud) vs typical on-premise data centers
- CO2e calculations account for Google Cloud's renewable energy procurement
- OCS = Optical Circuit Switches for dynamic topology reconfiguration

## Why This Matters

- 351 citations - authoritative source on specialized AI hardware efficiency
- Shows massive efficiency gains from purpose-built AI accelerators vs general GPUs
- 20x CO2e reduction demonstrates cloud + specialized hardware advantage
- Google is author - potential conflict of interest, but provides detailed methodology
- SparseCores example shows hardware-software co-design for efficiency
- Deployed at scale since 2020 - not theoretical, measured in production

## Caveats

- Paper authored by Google employees - obvious commercial interest
- Comparison is against "typical on-premise" which may not represent best-in-class
- Renewable energy procurement (Google) significantly impacts CO2e comparison
- Does not separate embodied vs operational emissions

---
Retrieved: 2026-01-16
Search: OpenAlex
