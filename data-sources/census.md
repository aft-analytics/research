# U.S. Census Bureau (data hub)

[census.gov/data.html](https://www.census.gov/data.html) — main Census data & maps hub. Explore/tables: [data.census.gov](https://data.census.gov/); developers: Census API.

**What it is:** Federal statistical source of truth for people, housing, and business *aggregates* (geography down to tract/block group/ZIP where disclosed) — not deeds, SOS entities, or parcel permits.

## Highest relevance for us

| Program | Use |
|---------|-----|
| **ACS** | Income, housing tenure, demographics for market/spectrum overlays |
| **BPS** ([census.gov/permits](https://www.census.gov/permits) — ASCII/Excel primary) | New residential permits by place/county/CBSA; HUD [SOCDS](hud-socds-permits.md) is a query UI over the same; FRED redistributes series only |
| **CBP** / **ABS** / Economic Census | Establishment counts by industry/geo |
| **Business Formation Statistics** | New-business application trends |
| **Population / housing estimates**, **SAIPE** | Local size & poverty |
| **LEHD / OnTheMap** | Workforce / commute |
| **TIGER** + Address Geocoder | Geo joins; address standardization aid |
| **Decennial** | Benchmark population/housing |

Also linked from hub: FTP downloads, Census Business Builder, MDAT (PUMS custom tables).

**Limit:** Disclosure-safe aggregates. For firm lists use SOS / [GovFiles](govfiles.md); for parcel building activity use city portals ([NYC](nyc-open-data.md)). Person-level ACS samples: [IPUMS USA](ipums-usa.md) (or Census PUMS). Often better to hit Census directly than via [data.gov](data-gov.md) metadata.
