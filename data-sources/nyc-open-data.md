# NYC Open Data (city)

[data.cityofnewyork.us](https://data.cityofnewyork.us/) — city Socrata portal. **Parcel/building grain** for NYC only; complements statewide [Open NY](data-ny-gov.md) (entities) and federal [data.gov](data-gov.md).

## Example: DOB Certificate of Occupancy

[bs8b-p36w](https://data.cityofnewyork.us/Housing-Development/DOB-Certificate-Of-Occupancy/bs8b-p36w) — legal use / permitted occupancy when DOB issues a CO (or TCO). Fields include job #, issue date, BIN/BBL/block-lot, address, dwelling units, lat/lon. Good for “was this building authorized for X units / use” — not ownership.

Related: [DOB NOW: Certificate of Occupancy](https://data.cityofnewyork.us/Housing-Development/DOB-NOW-Certificate-of-Occupancy/pkdm-hqz6).

## Other high-value NYC sets (same portal)

| Dataset | ID | Use |
|---------|-----|-----|
| DOB Permit Issuance | [ipu4-2q9a](https://data.cityofnewyork.us/Housing-Development/DOB-Permit-Issuance/ipu4-2q9a) | Building activity / renovation signal |
| ACRIS (deeds/mortgages — multi-table) | search “ACRIS” on portal | NYC property transfer & mortgage docs (ownership path) |
| PLUTO | [64uk-42ks](https://data.cityofnewyork.us/City-Government/Primary-Land-Use-Tax-Lot-Output-PLUTO/64uk-42ks) | Tax-lot land use / building attrs |
| Housing Litigations | [59kj-x8nc](https://data.cityofnewyork.us/Housing-Development/Housing-Litigations/59kj-x8nc) | Landlord/building distress |

**Limit:** NYC-only. Pattern to repeat for other cities’ open-data portals (permits, CoO, assessor) where national SOS/Census don’t reach parcel grain — e.g. [Austin Issued Construction Permits](austin-permits.md).
