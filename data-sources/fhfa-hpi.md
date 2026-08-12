# FHFA House Price Index (HPI)

Hub: [fhfa.gov/data/hpi](https://www.fhfa.gov/data/hpi) · downloads: [HPI datasets](https://www.fhfa.gov/data/hpi/datasets)

**Verdict:** Yes — free DIY **market / collateral stress overlays** (repeat-sales index). Not AVMs or parcel values.

| Grain | Cadence | Notes |
|-------|---------|--------|
| Nation / division / state / MSA | Monthly or quarterly | Master CSV (purchase-only, all-transactions, expanded) |
| County | Quarterly / annual packs | Good metro stress join |
| ZIP3 / ZIP5 / census tract | **Annual** developmental | Finest public HPI; not monthly |

No key. Prefer FHFA primary over FRED redistributes for full geo pack. Pair with [Zillow research CSVs](zillow-research.md) for monthly ZIP-ish ZHVI (different methodology / ToS).
