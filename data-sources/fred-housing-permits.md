# FRED — series tagged housing;permits

[fred.stlouisfed.org/tags/series?t=housing;permits](https://fred.stlouisfed.org/tags/series?t=housing%3Bpermits) — St. Louis Fed FRED catalog (~4k series with both tags). API: [fred.stlouisfed.org/docs/api](https://fred.stlouisfed.org/docs/api/fred/).

**What it is:** Redistributed **time series** of new privately owned housing units authorized by building permits (Census BPS / related constructions stats), packaged for charting and programmatic pull. Not a separate permit survey and not parcel records.

## Grain

- **Typical:** monthly units (SA / NSA) for **US**, **states**, and many **CBSAs/MSAs**; often split by structure (total, 1-unit, 2–4, 5+).
- **History:** national series from ~1959/1960; many state/MSA series from ~1988.
- **Not in this tag set as primary value:** county / permit-issuing place tables, parcel/address permits, or renovation/alteration microdata.

Popular examples on the tag page: US total & single-family authorizations; state series (CA, FL, TX, NY, WA…); MSA series (Seattle, DFW, Phoenix, Austin…).

## Vs Census BPS / HUD SOCDS

| | FRED tag | Census BPS / HUD SOCDS |
|--|----------|------------------------|
| Role | Convenience API + charts | Source of truth / place–county extracts |
| Geo | Mostly nation / state / MSA | Place, county, CBSA, state, US |
| Use | Macro / metro **market activity** overlays | Full jurisdiction coverage for local comps |
| Completeness | Curated series list (tag filter) | Full BPS universe (+ SOCDS UI) |

**Verdict:** Mild yes for easy state/MSA monthly pulls (API key) when we already trust BPS. Prefer Census BPS downloads or HUD SOCDS for county/place grain; prefer city open data for parcel permits. Do not treat FRED as a richer permit feed than Census.
