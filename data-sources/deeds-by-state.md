# Deeds / ownership — DIY vs national plant

**Decision:** For book-scale ownership overlays, buy a **national commercial plant** ([property-data-vendors.md](property-data-vendors.md)). DIY county recorders are free but fragmented (3,000+ jurisdictions, mixed UIs/vendors, little bulk API) — use for **spot checks**, pilots, or filling holes.

## Lanes

| Lane | What | When |
|------|------|------|
| National plant (ATTOM, DataTree, Cotality, …) | Licensed assessor + recorder/owner files; API/bulk/cloud | Portfolio match-append, production overlays |
| City/state open dumps | Structured microdata where published | Local depth (e.g. NYC ACRIS) |
| County recorder portals | Index + document images; often 3rd-party hosted | Manual / low-volume verification |
| Human abstractor (USTR, AFX) | Per-address PDF title research | Fraud/dispute exceptions — not overlays |

## DIY examples (open / portal)

| Place | Source | Notes |
|-------|--------|-------|
| **NYC** | [ACRIS](nyc-open-data.md) on NYC Open Data | Free deed/mortgage tables; NYC only |
| **DC** | [OTR Recorder of Deeds – Document Images](https://otr.cfo.dc.gov/service/recorder-deeds-document-images) | Online index/images from Aug 1921; “Online Public Records” leaves dc.gov → **private vendor site** — search UI, not a national bulk dump |
| **Other counties** | Assessor / recorder / clerk sites; many via Fidlar, Tyler, GovOS, etc. | Coverage and ToS vary; scraping usually fragile / restricted |

## Commercial shortlist

See **[property-data-vendors.md](property-data-vendors.md)** (ATTOM, CoreLogic/Cotality, DataTree, and peers). Per-report abstractors: [us-title-records.md](us-title-records.md).

## Related

- Parcel GIS clearinghouses: [purdue-gis-by-state.md](purdue-gis-by-state.md)
- LLC on title → SOS entities: [sos-bulk-by-state.md](sos-bulk-by-state.md), [govfiles.md](govfiles.md)
