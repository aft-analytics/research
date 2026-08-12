# HUD SOCDS Building Permits

[Portal](https://www.huduser.gov/portal/datasets/socds.html) → tool: [huduser.gov/socds/permits](https://www.huduser.gov/socds/permits) (gate: [`/terms-popup`](https://www.huduser.gov/socds/permits/terms-popup)). Guide: [PD&R Edge 2025-01](https://www.huduser.gov/archives/portal/pdredge/pdr-edge-spotlight-article-010725.html).

**What it is:** HUD PD&R query UI over **Census BPS** (new privately-owned residential permits). Only actively updated SOCDS dataset. Grain: **state / county / CBSA / permit-issuing jurisdiction** (~20k places) — units & valuation aggregates, **not** parcel permits.

**Access / terms:** Free public. Must accept standard U.S. Government information-system banner (monitoring/no privacy expectation) via `terms-accept` before the Query Tool. No separate data license beyond that.

**Download path:** After accept → Query Tool (geo × monthly prelim / monthly final / annual × SF/MF series) → **CSV**; **Summary** (state/CBSA high-level); **Help** links full-geography **MS Access** dumps. Same underlying series as [Census BPS](https://www.census.gov/permits) (ASCII/Excel) — prefer Census for bulk engineering; SOCDS for ad-hoc metro/place pulls.

**Takeaway:** Convenient HUD front-end to BPS already noted in [census.md](census.md) / [data-gov.md](data-gov.md). Use for housing-supply overlays at place/county; for parcel/reno signals use city portals ([NYC](nyc-open-data.md)), not SOCDS.
