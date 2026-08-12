# BLS (labor / local economy)

Hub: [bls.gov](https://www.bls.gov/) · [Public Data API](https://www.bls.gov/developers/) (register; v2 higher limits) · flat files under `download.bls.gov/pub/time.series/`.

**Verdict:** Yes for **local labor / stress overlays**. Aggregates only — not employer or person lists.

| Program | Grain | Use |
|---------|-------|-----|
| **LAUS** | State / metro / county / many cities | Unemployment & labor force (monthly) |
| **QCEW** | County × industry (NAICS) | Employment & wages — establishment aggregates |
| **CES / CPS** | Nation / state (select) | Macro employment — deck more than ZIP overlays |
| **OEWS** | Metro / state occupation wages | Wage benchmarks |

Prefer BLS primary (or FRED for single series) over [Data USA](datausa.md). Pair with ACS / [IRS SOI ZIP](irs-soi-zip.md) for income mix; Census CBP for establishment counts ([census.md](census.md)).
