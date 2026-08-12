# HMDA (Home Mortgage Disclosure Act)

**Verdict:** Free DIY via the FFIEC/CFPB HMDA Platform. **Loan-application grain → census tract** (not borrower/property address). Good for **market mix / spectrum / lender competitive overlays**. **Not** a loan-tape substitute (no ULI, no address, amounts/income privacy-rounded, no credit scores).

Hub: [ffiec.cfpb.gov](https://ffiec.cfpb.gov/) · overview [CFPB HMDA](https://www.consumerfinance.gov/data-research/hmda/) · catalog pointer [data.gov](data-gov.md). Prefer the platform over catalog metadata.

## Piecing order (recommended)

1. **Browse / slice:** [Data Browser](https://ffiec.cfpb.gov/data-browser/) (Dataset Filtering / maps / graphs) — pick year + geo or LEI; download filtered CSV or view aggregates.
2. **Bulk national LAR:** [Data Publication](https://ffiec.cfpb.gov/data-publication/) → **Snapshot** (and later One-Year / Three-Year) National Loan-Level Dataset — full-year pipe-delimited / CSV from public files (`files.ffiec.cfpb.gov`).
3. **One lender:** [Modified LAR](https://ffiec.cfpb.gov/data-publication/modified-lar) by **LEI** (UI or File API) — early spring release; fewer derived/Census appends than summer Snapshot.
4. **Programmatic subsets:** [Data Browser API](https://ffiec.cfpb.gov/documentation/api/data-browser/) (`/v2/data-browser-api/view/...`) — year + ≥1 HMDA filter; nationwide or geo/LEI-scoped CSV/JSON aggregations. No key for public endpoints.
5. **Filer roster:** Data Browser API `…/view/filers?years=` — institutions present for a year (LEI join key).

## Grain & lending fit

| Product | Grain you actually get | Fit for us |
|---------|------------------------|------------|
| **Modified LAR** (spring, per LEI or combined) | One row ≈ **application / covered loan action**; geo = state / county FIPS / **11-digit census tract**; street/city/ZIP **redacted** | Fast peer / book mix by lender×tract; privacy mods apply |
| **Snapshot / One-Year / Three-Year National LAR** | Same loan-app grain + **derived** race/ethnicity/sex + **appended tract Census attrs** (minority %, tract-to-MSA income %, etc.) | Prefer for research panels / spectrum overlays; freeze dates differ (filers may resubmit ~3y) |
| **Dynamic National LAR** | Same schema; updates as resubmissions land | Freshest public file; less “fixed benchmark” than Snapshot |
| **Data Browser aggregates** | Counts/sums by chosen dimensions | Quick market-share charts — not microdata |

**Privacy / redaction (public LAR):** ULI, application & action dates, property street/city/ZIP, credit score, AUS result, NMLS MLO ID, free-form race/ethnicity text **excluded**. Loan amount → midpoint of nearest **$10k** bucket; income (thousands) and some ratios similarly coarsened. Age mostly bucketed (+ ≥62 flags).

**Years:** Modern public fields roughly **2018+** (post–2015 rule expansion). Historic (pre-2018 / different schema) via HMDA historic data pages on the same platform — don’t mix schemas casually. Filing year = calendar year of action; annual file due ~Mar 1 next year; Snapshot typically ~May.

## Fields that matter for us

| Need | Fields (public names vary slightly by product) |
|------|--------------------------------------------------|
| Purpose / product | `loan_purpose`, `loan_type`, `lien_status`, `occupancy_type`, `construction_method`, reverse / open-end flags |
| Size | `loan_amount` (rounded), `income` (thousands, modified), sometimes DTI / rate spread / HOEPA |
| Outcome | `action_taken` (originated, denied, purchased, withdrawn…) |
| Demographics (aggregates) | Race / ethnicity / sex (raw multi-codes + **derived_*** on Snapshot); use for **area / book mix**, not person match |
| Lender | **`lei`**; agency code / respondent IDs on some products; filer list API |
| Geography | `state_code`, `county_code`, `census_tract`, `derived_msa_md` |
| Secondary | `purchaser_type` (GSE / private / etc.) |
| Tract context (Snapshot+) | `tract_minority_population_percent`, `tract_to_msa_income_percentage`, owner-occupied / 1–4 unit counts, etc. |

Dicts: [MLAR 2018+](https://ffiec.cfpb.gov/documentation/publications/modified-lar/resources/data-dictionaries/mlar-dd-2018-onward) · [Public LAR schema](https://ffiec.cfpb.gov/documentation/publications/loan-level-datasets/public-lar-schema) · [derived / Census appends](https://ffiec.cfpb.gov/documentation/publications/general/derived-data-fields).

## DIY — primary URLs

| Piece | Where | Notes |
|-------|-------|-------|
| Platform home | [ffiec.cfpb.gov](https://ffiec.cfpb.gov/) | Filing + public data |
| Data Browser UI | [/data-browser/](https://ffiec.cfpb.gov/data-browser/) | Filter → CSV / aggregates |
| Data Browser API | [docs](https://ffiec.cfpb.gov/documentation/api/data-browser/) | `view/csv`, `view/nationwide/csv`, `view/aggregations`, `view/filers` |
| Modified LAR | [/data-publication/modified-lar](https://ffiec.cfpb.gov/data-publication/modified-lar) | Per-LEI + combined; [File API](https://ffiec.cfpb.gov/documentation/api/file-serving/) |
| Snapshot / static national | [/data-publication/](https://ffiec.cfpb.gov/data-publication/) (Snapshot, One-Year, Three-Year) | Bulk on `https://files.ffiec.cfpb.gov/` |
| Dynamic national | Data Publication → Dynamic National Loan-Level Dataset | Rolling updates |
| Aggregate & disclosure reports | Data Publication | Institution / MSA tables — deck-friendly |
| CFPB explainer | [Beginner’s guide / HMDA research](https://www.consumerfinance.gov/data-research/hmda/) | Concepts + access tips |
| data.gov | Search “HMDA” | Finder only |

## Limits (don’t pretend otherwise)

- **Not address / parcel / loan-tape.** Cannot join to a specific borrower or APN.
- Covered institutions + covered applications only (thresholds / exemptions) — not the entire mortgage market.
- Amounts and income are **coarsened**; denials/AUS/credit detail largely **gone** from public files.
- Schema break at **2018**; resubmissions mean Snapshot ≠ final Three-Year for the same year.
- Huge files — prefer Data Browser filters or per-LEI MLAR unless you need the national dump.

## Adjacent (don’t redo)

- **Bank / CU call reports, NIC, SOD, NCUA 5300, FINRA BD lists:** already in [us-banks.md](us-banks.md) / [fi-data-vendors.md](fi-data-vendors.md). HMDA LEI overlays market activity; call reports overlay balance-sheet — different jobs.
- **FHFA HPI / Zillow:** house-price market context — [fhfa-hpi.md](fhfa-hpi.md), [zillow-research.md](zillow-research.md).
- **Loan tapes (dv01, warehouse):** performance / tape fields — [dv01.md](dv01.md) (evaluated — pending commercial / use-case OK); not HMDA.

## Related

- FI DIY directories / financials: [us-banks.md](us-banks.md)
- Catalog finder: [data-gov.md](data-gov.md)
- Tract / ACS demographics join: [census.md](census.md)
