# Open NY (data.ny.gov)

[data.ny.gov](https://data.ny.gov/) — NYS open data (~1k+ datasets; Socrata). State-level; **not** NYC deeds/permits (see [NYC Open Data](nyc-open-data.md) — ACRIS, DOB CoO/permits).
## High value for us

| Dataset | ID / link | Why |
|---------|-----------|-----|
| **Active Corporations** (DOS) | [n9v6-gdp6](https://data.ny.gov/Economic-Development/Active-Corporations-Beginning-1800/n9v6-gdp6) | Free NY entity dump: DOS ID, name, type, jurisdiction, process address, CEO fields; monthly as-of |
| Corporations & Other Entities: All Filings | [63wc-4exh](https://data.ny.gov/Economic-Development/Corporations-and-Other-Entities-All-Filings/63wc-4exh) (+ name/status history tables) | Filing history companion |
| Property assessment / parcel counts | e.g. [7vem-aaz7](https://data.ny.gov/Government-Finance/Property-Assessment-Data-from-Local-Assessment-Rol/7vem-aaz7), [tnwc-mx3q](https://data.ny.gov/Government-Finance/Parcel-Counts-By-Type-By-Municipality-Beginning-Ro/tnwc-mx3q) | Local tax-roll style aggregates — not statewide deed records |
| SONYMA loans / target areas | [22ew-dxez](https://data.ny.gov/Housing-Development/State-of-New-York-Mortgage-Agency-SONYMA-Loans-Pur/22ew-dxez) | Housing program loans, not consumer credit |

## Weak / missing here

- Statewide **deeds** / recorder microdata  
- Parcel-level **building permits** (only thin local/code-report scraps)  
- **NFIP**/flood overlays (use OpenFEMA)  
- **UCC** bulk not really present (Pierce: NY SOS bulk status unclear)

**Takeaway:** Best open-state SOS-style dump we’ve seen after CT — pull Active Corporations for NY DIY entity file; don’t expect deeds/permits national coverage from this portal.
