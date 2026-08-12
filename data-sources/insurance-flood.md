# Insurance / flood / hazard overlays (DIY + light vendors)

**Verdict:** For **lending overlays**, DIY federal stack covers (1) **SFHA / flood-zone join at address/parcel** via NFHL GIS, (2) **NFIP policy & claim history at tract/ZIP** (redacted — not property match), (3) **disaster designation at county**. Property-level climate scores, private-market flood, wildfire/quake plants → **vendors**.

Hubs: [OpenFEMA data sets](https://www.fema.gov/about/openfema/data-sets) · [API docs](https://www.fema.gov/about/openfema/api) (free, no key) · catalog pointer [data.gov](data-gov.md). Prefer agency pages over catalog metadata.

## Piecing order (recommended)

1. **Flood zone at collateral:** geocode address → point-in-polygon on **NFHL** (effective FIRM SFHA / zone) — MSC county/state downloads or ArcGIS REST.
2. **NFIP book / loss context:** OpenFEMA **redacted policies + claims** (v3) — aggregate by census tract / ZIP / county / flood zone; do **not** expect address join.
3. **Event flags:** OpenFEMA **Disaster Declarations Summaries** (county × declaration) ± Web Disaster Declarations geo files.
4. **Community eligibility / CRS:** NFIP Community Status Book (+ community layers if mapping).
5. **Multi-hazard market overlay (coarse):** [National Risk Index](https://www.fema.gov/about/openfema/data-sets/national-risk-index-data) — county / census tract scores for 18 perils (not parcel).

## Grain & lending fit

| Source | Grain you actually get | Fit for lending overlays |
|--------|------------------------|--------------------------|
| **NFHL / FIRM GIS** | Flood hazard **polygons** (SFHA, zone AE/VE/X…, BFE attrs where mapped); join via lat/lon or parcel centroid | **Best DIY property flag** — mandatory-purchase / SFHA / zone class. Coverage gaps where no digital effective NFHL. |
| **NFIP redacted policies** | One row ≈ **policy period**; geo = census tract, reported ZIP, county FIPS; lat/lon to **0.1°** only | Penetration / rating / coverage mix by area — **not** “does this loan’s house have NFIP.” ~monthly; prefer **v3**. |
| **NFIP redacted claims** | One row ≈ **claim**; same geo redaction; paid amounts, rated zone, dates | Area loss history / severe-loss signals at tract/ZIP — **not** per-address claim file. Prefer **v3** (v2 deprecated ~2026-10). |
| **Disaster declarations** | **County** (designated area) × disaster since 1953; programs IA/PA/HM flags | Portfolio stress / event exposure by county — not parcel damage. |
| **Community Status Book** | **NFIP community** participation + CRS discount rates | Community eligibility / CRS class — join via community ID, not APN. |
| **National Risk Index** | County + **census tract** expected annual loss / risk indices | Coarse multi-peril market overlays; not underwriting property risk. |

## DIY — primary URLs

| Piece | Where | Notes |
|-------|-------|-------|
| OpenFEMA hub | [Data sets](https://www.fema.gov/about/openfema/data-sets) | CSV/JSON/Parquet + API; page `$top` (max 10k) or bulk files for NFIP |
| NFIP policies (current) | [NfipRedactedPolicies v3](https://www.fema.gov/openfema-data-page/nfip-redacted-policies-v3) · API `…/api/open/v3/NfipPolicies` | Policies since ~2009; huge — use Parquet/CSV dump |
| NFIP claims (current) | [NfipRedactedClaims v3](https://www.fema.gov/openfema-data-page/nfip-redacted-claims-v3) · API `…/api/open/v3/NfipClaims` | Claims ~1978–present; same redaction as policies |
| Legacy FIMA v2 | still listed; **deprecated**, frozen, remove by ~2026-10-15 | Migrate to v3 names (no `Fima` prefix) |
| Disaster declarations | [DisasterDeclarationsSummaries v2](https://www.fema.gov/openfema-data-page/disaster-declarations-summaries-v2) · `…/api/open/v2/DisasterDeclarationsSummaries` | County FIPS + incident type/dates |
| Web disaster + areas | [FemaWebDisasterDeclarations](https://www.fema.gov/openfema-data-page/fema-web-disaster-declarations-v1); [FemaWebDeclarationAreas](https://www.fema.gov/openfema-data-page/fema-web-declaration-areas-v1) | One-row-per-disaster pages; shapefile/KMZ links from ~2010 |
| Community Status Book | [NfipCommunityStatusBook v1](https://www.fema.gov/openfema-data-page/nfip-community-status-book-v1) | Participation + CRS SFHA/non-SFHA discounts |
| NFIP community polygons | OpenFEMA NFIP Community Layer (comprehensive / no-overlaps) | Map communities, not buildings |
| Multiple-loss / penetration | OpenFEMA NFIP Multiple Loss Properties; Residential Penetration Rates | Still area/program grain — check dict before treating as address |
| **NFHL (FIRM GIS)** | [NFHL overview](https://www.fema.gov/flood-maps/national-flood-hazard-layer); [MSC Search All Products](https://msc.fema.gov/portal/advanceSearch) (NFHL Data–County/State); [REST MapServer](https://hazards.fema.gov/arcgis/rest/services/public/NFHL/MapServer) | Shapefile/GDB downloads; WFS capped (~1k features) — prefer county/state packs for bulk |
| National Risk Index | [NRI downloads](https://www.fema.gov/about/openfema/data-sets/national-risk-index-data) | Tract/county tables + GIS; files-only on OpenFEMA list |
| data.gov | Search “OpenFEMA” / “NFIP” / “NFHL” | Finder only — land on FEMA pages above |

**Redaction reality (policies/claims):** PII stripped; location ≈ tract + ZIP + 0.1° lat/lon. Points cluster; may fall in wrong county if you trust lat/lon alone — FEMA says use state/county fields for aggregation.

## Vendor / hazard peers (optional further diligence)

| Vendor | One-liner |
|--------|-----------|
| **First Street** | Property-level climate risk (flood / wildfire / wind / heat…); API + portfolio suite — licensed |
| **Cotality (CoreLogic) Climate & Hazard** | Institutional hazard / climate analytics on parcel plant — see [property-data-vendors.md](property-data-vendors.md) |
| **Verisk / AIR, Moody’s RMS** | Cat models & scores (insurer/lender grade) — enterprise |
| **ATTOM / peers** | Some hazard appends on property APIs — confirm vs Cotality/First Street if buying dedicated scores |

**Vendor-only (or near-only) products:** true **address-matched** NFIP/private flood policy status, carrier quotes, forward climate damage/AAL at structure, wildfire/quake underwriting scores, nationwide private-flood market files. DIY does **not** replace those.

## Related

- Catalog finder: [data-gov.md](data-gov.md)
- Parcel GIS clearinghouses (join geometry): [purdue-gis-by-state.md](purdue-gis-by-state.md)
- Property plant for APN/owner match-append: [property-data-vendors.md](property-data-vendors.md), [attom.md](attom.md)
