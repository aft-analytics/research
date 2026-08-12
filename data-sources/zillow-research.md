# Zillow Research (ZHVI / ZORI / inventory)

Hub: [zillow.com/research/data](https://www.zillow.com/research/data/) — free public CSVs (CDN `files.zillowstatic.com/research/public_csvs/…`).

**Verdict:** Yes for **housing market overlays** (typical values, rents, inventory). Not ownership / deeds; not a property plant ([property-data-vendors.md](property-data-vendors.md)).

| Series | Grain | Notes |
|--------|-------|--------|
| **ZHVI** | Nation → ZIP / neighborhood | Monthly typical home value (mid-tier etc.) |
| **ZORI** | Similar subset | Observed rents |
| Inventory / DOM / list cuts | Metro / ZIP varies | Liquidity / stress signals |

No public query API for these metrics (CSV download). Attribution required; confirm ToS for commercial product use. ZTRAX / Bridge = separate licensed parcel/transaction path — not the free research CSVs.

**Vs FHFA HPI:** [FHFA](fhfa-hpi.md) = GSE repeat-sales official index (ZIP/tract often annual); Zillow = listing/model-based typical value, often monthly ZIP. Use both lightly; neither replaces AVMs for underwriting.
