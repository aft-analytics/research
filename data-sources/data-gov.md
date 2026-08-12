# data.gov catalog

[catalog.data.gov](https://catalog.data.gov/) — GSA metadata index (~550k federal/state/local datasets). **Finder, not a warehouse:** follow through to agency downloads/APIs. Search API: `api.gsa.gov/technology/datagov/v4` (needs api.data.gov key).

## Fit for our domains (federal hits)

| Domain | On data.gov / linked agencies | Notes |
|--------|-------------------------------|--------|
| Building permits | Census **BPS** ([census.gov/permits](https://www.census.gov/permits)); HUD [SOCDS](hud-socds-permits.md) (BPS place/county/CBSA UI) | Place/county aggregates — not parcel permits |
| Insurance / disaster | **OpenFEMA** NFIP redacted claims & policies; NFIP community status/CRS; disaster declarations; NFHL via FEMA MSC (not only catalog) | Strong — detail in [insurance-flood.md](insurance-flood.md) |
| Mortgage / credit public | **HMDA** (CFPB); CRA analytics tables (Fed) | Loan-application grain (HMDA), not consumer bureau |
| Housing prices | **FHFA HPI** | Metro/ZIP-ish indexes |
| Local economy / mix | **ACS** / **BFS** / **CBP** — prefer [Census hub](census.md); **IRS SOI ZIP** | Spectrum / market overlays |
| Banks / CUs | **FDIC** institutions (+ NCUA outside/near catalog) | Txn string matching |
| Small-business credit | **SBA** 7(a)/504 & disaster loan reports | Portfolio research, not consumer |

## Weak / absent on data.gov (catalog limits)

- Full **SOS entity** registries (state portals / [GovFiles](govfiles.md) / [SOS bulk](sos-bulk-by-state.md))
- **Deeds / assessor** national files (county / commercial)
- **USPS NCOA** (licensed, not open)
- Parcel-level permits (city open data, not Census BPS)

## How to use

Search catalog → open agency source of truth → prefer CSV/API with documented grain. State/city catalogs also harvest here (e.g. WA business lookup, local crime) but coverage is uneven — treat as discovery, then bookmark the primary URL.
