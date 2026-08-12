# Data sources

Inventory of datasets / data products we might access for credit, market, overlays, and fraud. Prefer usable grain (ZIP / parcel / loan / person / firm) and a clear access path.

## What to explore (from the ask + ideas)

| Domain | Why | Examples to dig |
|--------|-----|-----------------|
| Public records / deeds | Verify homeownership; LLC + articles of incorp when name isn’t on title | [Deeds DIY vs plant](deeds-by-state.md); [property vendors vs ATTOM](property-data-vendors.md); [ATTOM](attom.md); [county recorder DIY](county-recorder-diy.md); [USTR abstractor](us-title-records.md) |
| Housing & valuations | Collateral / housing-status signal; market stress | ACS, Zillow/FHFA indexes; GIS parcels ([Purdue GIS guide](purdue-gis-by-state.md)); [property-data-vendors.md](property-data-vendors.md) |
| Building permits | Local activity, renovation, investor vs owner signals | [BuildZoom / Gryd](buildzoom.md); [SATT residential (Databricks)](satt-building-permits.md); Census BPS ([census.md](census.md) / [data.gov](data-gov.md)); [HUD SOCDS](hud-socds-permits.md); [FRED housing;permits](fred-housing-permits.md); [WCRER WA](wcrer-permits.md); [NYC Open Data](nyc-open-data.md) (DOB); [Austin permits](austin-permits.md); Shovels-class peers; other city portals |
| Insurance | Disaster / flood / property risk overlays | OpenFEMA NFIP + disasters ([data.gov](data-gov.md)); NAIC / DOI; hazard vendors |
| US companies / entities | Firm graph for LLC ownership, employers, merchants | [GovFiles](govfiles.md); [SOS bulk by state](sos-bulk-by-state.md); [CompanyData](companydata.md); OpenCorporates; SEC EDGAR |
| USPS address changes | Fraud / instability (NCOA moves) | USPS NCOA<sup>Link</sup> / AIS (licensed); not free bulk |
| Financial institutions | Better parse of banks / CUs / brokers in txn text | FDIC institutions; NCUA credit unions; FINRA BrokerCheck data |
| Loan tapes | Fit external tapes into Runway | dv01 (talk next week); other ABS/warehouse tape providers |
| Credit & mortgage public filings | Book / market benchmarks | HMDA; FFIEC/FDIC call reports |
| Labor / income / local economy | Spectrum / market mix overlays | [Census hub](census.md); [IPUMS USA](ipums-usa.md) (ACS PUMS microdata); BLS; IRS SOI ZIP |

Already in hand / partial: US location datasets for txn geo; mediocre bank/CU/broker string detection (improve with institution lists above). Research papers live under `notes/` / `papers/`, not here.

## Evaluated

| Source | What it is | Useful for us? | Notes |
|--------|------------|----------------|-------|
| [Statista](statista.md) | Curated aggregates and published charts | Mostly no | Not microdata; deck/macro only. |
| [CompanyData USA](companydata.md) | SOS/SEC-based firm file (~65M+) | No for full dump | ~$30k/1M; prefer DIY state SOS for bulk. |
| [GovFiles](govfiles.md) | Normalized SOS entities (~75M+), API + Parquet | Likely yes — sample | $0.01/row or $499/100k; bulk custom. Best commercial fit so far. |
| [SOS bulk by state](sos-bulk-by-state.md) | Official registry dump availability matrix | Yes as map | ~27 have bulk (4 free); CA/DE no official dump. |
| [Census Bureau hub](census.md) | census.gov/data.html + data.census.gov / API | Yes | ACS, BPS, CBP, BFS, SAIPE, TIGER — aggregates, not firms/deeds. |
| [IPUMS USA](ipums-usa.md) | Harmonized ACS/census **microdata** (PUMS) | Yes for research | Person/HH grain; PUMA not address; free w/ register. |
| [data.gov catalog](data-gov.md) | Federal/state open-data index | Yes as finder | Points at Census/FEMA/HMDA/etc.; prefer agency hubs. |
| [Open NY](data-ny-gov.md) | NYS open data portal | Yes for NY entities | Free DOS Active Corporations dump; assessment aggregates; not deeds. |
| [NYC Open Data](nyc-open-data.md) | City building/housing microdata | Yes for NYC | DOB CoO/permits, ACRIS, PLUTO — parcel grain; NYC only. |
| [Austin permits](austin-permits.md) | City issued construction permits (Socrata) | Yes for Austin | ~2.4M rows, daily; address/TCAD/lat-lon; BLDS; not ownership. |
| [State open data portals](state-open-data-portals.md) | Forbes 2018 50-state (+DC/PR) list | Yes as map | Stale links; mix of catalogs / transparency / GIS. |
| [State portals spot-check](state-portals-spotcheck.md) | Live VA + peer catalog probes | Yes | VA SCC LLC/corp; CT/NY/CO/OR/PA entities; NJ permits. |
| [Purdue GIS by state](purdue-gis-by-state.md) | LibGuide of state GIS clearinghouses | Yes for parcels/geo | PASDA, MassGIS, AGRC, TNRIS, VGIN…; not SOS entities. |
| [Georgetown US datasets](georgetown-us-datasets.md) | Stats pathfinder (Census, data.gov, DC) | Mild | Mostly hubs we already have; some licensed-only. |
| [Data USA](datausa.md) | Viz/API over public US gov aggregates | Mild | Place/industry reports; not firms/deeds. Prefer Census primary. |
| [ED Open Data](data-ed-gov.md) | data.ed.gov (~1k profiles) | Yes if student loans | Scorecard, CDRs, FSA portfolio; not NSLDS borrower dump. |
| [DOT Open Data](data-transportation-gov.md) | data.transportation.gov (+ BTS) | Niche | FMCSA carrier census; freight/mobility stats. |
| [HUD SOCDS permits](hud-socds-permits.md) | HUD UI over Census BPS | Mild | Place/county/CBSA aggregates; click-through gov terms; prefer Census ASCII for bulk. |
| [BuildZoom / Gryd](buildzoom.md) | National permits + contractors (380M+, 25y) | Likely yes — quote | Property grain; Explorer $150–480/mo/state; API/bulk custom. vs Shovels (peer), BPS (aggregates), NYC DOB (free, NYC-only). |
| [SATT residential permits](satt-building-permits.md) | Databricks Marketplace permit share (residential) | Maybe — sample | ~300K active projects; weekly / 6-wk window; paid by request ($199–$1,999+/mo on vendor site). Peer to BuildZoom/Shovels; not BPS/SOCDS aggregates. |
| [WCRER permits/completions](wcrer-permits.md) | UW WA toolkit: BPS permits + OFM completions | Mild — WA only | County/place Excel; completions add-on; not national/parcel. |
| [FRED housing;permits](fred-housing-permits.md) | ~4k FRED series (Census BPS redistributed) | Mild | Easy state/MSA monthly API; prefer BPS/SOCDS for place/county. |
| [Deeds DIY vs plant](deeds-by-state.md) | Framing: county portals vs national plants | Yes as map | DIY for spot checks; plant for overlays; DC ROD + NYC ACRIS examples. |
| [Property data vendors](property-data-vendors.md) | ATTOM + snowballed national peers | Yes — shortlist | DataTree/Cotality closest plants; BatchData/Regrid/Melissa self-serve-ish; USTR/AFX abstractor lane. |
| [ATTOM](attom.md) | Assessor + recorder/deed plant; API + Databricks | Likely yes — quote/trial | Baseline ownership overlay vendor. |
| [County recorder DIY](county-recorder-diy.md) | Portal pattern (often vendor-hosted) | Mild | No national bulk; use with deeds-by-state. |
| [U.S. Title Records](us-title-records.md) | Per-report human title abstractor | Exception only | $29–275+/report; not a deed dump. |

## Backlog (not yet evaluated)

Add a row (and optional `data-sources/<name>.md`) as each source gets a pass:

- More states from Forbes list (FL, GA, CA SOS path, IL live URL)
- Municipal list from Forbes companion (90 cities) + [NYC](nyc-open-data.md) / [Austin](austin-permits.md)
- USPS NCOA (access + cost)
- OpenCorporates (vs GovFiles / DIY SOS bulk)
- NCUA (alongside FDIC from data.gov)
- dv01 loan tapes
- Pull primary URLs for BPS / OpenFEMA / HMDA / FHFA / IRS SOI ZIP into short notes
