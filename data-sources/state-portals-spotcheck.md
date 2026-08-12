# State open-data portals — spot checks

Live probes of portals from the [Forbes 2018 list](state-open-data-portals.md) for **entities / permits / parcels**. Not exhaustive; catalogs also harvest federal noise.

## Virginia — [data.virginia.gov/dataset](https://data.virginia.gov/dataset)

CKAN, **~33k** packages (heavy harvest). **High value:** State Corporation Commission dumps:

| Dataset | Link |
|---------|------|
| Corporation | [/dataset/corporation](https://data.virginia.gov/dataset/corporation) (XLSX) |
| LLC | [/dataset/llc-limited-liability-company](https://data.virginia.gov/dataset/llc-limited-liability-company) (CSV) |
| Name History, Merger, Amendment, Business Trusts, PSA… | SCC org on portal |
| UCC Filing Details / Lien Details | SCC |

Also: **local** building permits & parcels (VA Beach, Loudoun, Fairfax, etc.) — not statewide. Modern deeds ≠ historical manumission sets.

## Strong entity / business files elsewhere

| Portal | Find | Notes |
|--------|------|--------|
| [data.ct.gov](https://data.ct.gov) | Business Registry Master + Agent/Principal/Filing/Name History | Free nightly; see [sos-bulk](sos-bulk-by-state.md) |
| [data.ny.gov](https://data.ny.gov) | Active Corporations | See [data-ny-gov](data-ny-gov.md) |
| [data.colorado.gov](https://data.colorado.gov) | [Business Entities in Colorado](https://data.colorado.gov/Business/Business-Entities-in-Colorado/4ykn-tg5h) (+ transaction history, UCC tables) | Daily open-data; matches free bulk tier |
| [data.oregon.gov](https://data.oregon.gov) | [Active Businesses - ALL](https://data.oregon.gov/Business/Active-Businesses-ALL/tckn-sxa6) | Registry #, addresses, agents (~527 datasets total) |
| [data.pa.gov](https://data.pa.gov) | [Registered Businesses … by County](https://data.pa.gov/Licenses-Certificates/Registered-Businesses-in-PA-Current-by-County-Depa/xvd7-5r2c) | DOS; distinct-entity view linked from desc |
| [data.texas.gov](https://data.texas.gov) | [Active Franchise Taxpayers](https://data.texas.gov/Government-and-Taxes/Active-Franchise-Taxpayers/9cir-efmm) | Comptroller (not full SOS); ~822 datasets; thin permits |

## Permits / parcels (state-level useful)

| Portal | Find |
|--------|------|
| [data.nj.gov](https://data.nj.gov) | [NJ Construction Permit Data](https://data.nj.gov/Energy-and-Environment/NJ-Construction-Permit-Data/w9se-dmra) — statewide municipal permit reporting |
| CT | Annual housing permits by town; **2024/2025 Parcel and CAMA** |
| CO | Building permit *counts*; Denver/county parcels |
| VA / WA | Mostly **city/county** permit layers, not one state file |
| CA [data.ca.gov](https://data.ca.gov) | ~4.5k sets; tax/corp *stats*, well permits — **no** clear SOS entity dump in quick search |

## Weak / wrong for our ask (sampled)

| Portal | Reality |
|--------|---------|
| Forbes CT transparency URL | Prefer **data.ct.gov** |
| data.illinois.gov | No Socrata catalog response (dead/moved?) |
| data.wa.gov | Licenses/contractors; UBI hits were **county-scoped**, not full SOS |
| Many Forbes “open” links | Budget/transparency only (AZ OpenBooks, KY/OH transparency, etc.) |

## Takeaway

Prioritize portals that already publish **entity master files** (VA SCC, CT, NY, CO, OR, PA) + **NJ permits** + city portals ([NYC](nyc-open-data.md)). Use Forbes list as seeds; re-verify URL and search `corporation` / `business entity` / `permit` / `parcel` before counting a state as covered.
