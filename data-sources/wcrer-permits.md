# UW WCRER — Permits and Completions

[wcrer.be.uw.edu/…/permits-and-completions](https://wcrer.be.uw.edu/housing-market-data-toolkit/permits-and-completions/) — Washington Center for Real Estate Research (UW) Housing Market Data Toolkit page.

**What it is:** WA-focused curated downloads, not a new survey. Residential **permits** are from Census **BPS**; **housing stock / completions** are estimated from WA Office of Financial Management (OFM) annual unit counts. Toolkit also has city/county dashboards elsewhere on the site.

## Grain & refresh

| Product | Geography | Grain / history | Update |
|---------|-----------|-----------------|--------|
| [Residential Building Permit Report](https://wcrer.be.uw.edu/wp-content/uploads/sites/60/2025/09/County-and-Place-Building-Permit-Data-Report-Q2-2025.xlsx) (XLSX) | WA counties + census places (cities/towns/CDPs) | Annual (~10y) + YTD; SF vs MF units | Quarterly |
| [Housing Completions Report](https://wcrer.be.uw.edu/wp-content/uploads/sites/60/2025/09/Housing-Completions-Report-2025.xlsx) (XLSX) | WA counties, cities, towns | Stock from 2020; completions from 2020–21 | Annual |

**Not:** parcel / address permits, national coverage, or investor/renovation microdata.

## Vs Census BPS / HUD SOCDS

| | WCRER | Census BPS / HUD SOCDS |
|--|-------|------------------------|
| Coverage | **Washington only** | National (place/county/CBSA/state) |
| Permits | BPS redistributed, WA-sliced Excel | Primary (BPS) or HUD query UI (SOCDS) |
| Completions | **OFM-estimated** stock change (WA value-add) | BPS is authorizations, not completions |
| Access | Hand-updated toolkit XLSX / dashboards | Census ASCII/API; SOCDS tables |

**Verdict:** Mild — handy WA packaging + OFM completions. Prefer [Census BPS](census.md) / HUD SOCDS for national place/county permits; use city portals ([NYC](nyc-open-data.md)) for parcel grain. Skip as a national permit source.
