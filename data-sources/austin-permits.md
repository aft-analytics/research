# Austin Open Data — Issued Construction Permits

[data.austintexas.gov](https://data.austintexas.gov/) — city Socrata portal (peer pattern to [NYC Open Data](nyc-open-data.md)). Parcel/address grain for Austin / Travis CAD only.

## Issued Construction Permits

[3syk-w9eu](https://data.austintexas.gov/Building-and-Development/Issued-Construction-Permits/3syk-w9eu) — building, electrical, mechanical, plumbing, and driveway/sidewalk permits issued by Austin Development Services. ~2.4M rows; **daily** refresh; coverage **1980–present**. BLDS-compliant.

**Grain:** one row per issued permit. Join keys: address / ZIP, lat/lon, **TCAD ID** (Travis CAD Geographic ID), project/master permit IDs.

**Useful fields:** permit type/class (res vs commercial), work class, description, issue/status/complete dates, valuation + remodel sqft, housing units, contractor/applicant, CoO required flag, council district / jurisdiction.

**Use:** local renovation / new-construction activity signal; investor vs owner heuristics via contractor + valuation; not ownership or deeds.

**Limit:** Austin jurisdiction only; department disclaimer — informational, may lag/differ from official AB+C. Portal also has GIS (ArcGIS Online) and other building/land-dev sets worth browsing for CoO / inspection peers.
