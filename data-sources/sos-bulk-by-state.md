# State SOS bulk registry data (Private Pierce matrix)

[Explainer](https://privatepierce.com/business-formation/business-registry-bulk-data-availability-by-state-explainer/) · [Matrix](https://privatepierce.com/business-formation/business-registry-bulk-data-availability-by-state/) (checked ~2026-05/06)

Third-party survey of **official** bulk business-registry exports (not portals, not brokers).

**Headline:** ~27 jurisdictions have some official bulk path; ~20 do not; 4 unconfirmed (NY/VT/WA/WY).

**Free direct:** AK, CO (daily CSV on open data), CT (nightly), OH (monthly). HI = low-barrier list builder.  
**CT gold standard:** [Bulk Data and Images](https://portal.ct.gov/sots/business-services/bulk-data-and-images) — free nightly extracts on **data.ct.gov** (Business Master + Agent + Principal + Filing + Name History); UCC liens free; UCC *images* $1k/yr. Portal search export capped at 1k rows.

**No official bulk (notable):** CA, DE, OR, plus AL/AZ/DC/IL/KS/LA/MD/MO/MS/NE/NH/NM/PA/RI/SC/TN/VA.

**Paid / request:** e.g. TX SOSDirect, IN/KY/MN/NV/NC/… subscriptions or APIs; FL FOIA-style. Matrix understates some products — verify current portals:
- **[GA bulk FTP](https://georgia.gov/bulk-corporations-data)** — $1k one-time or $500/mo (+ $100 account); space-delimited FTP
- **[AR Corp Bulk Download](https://portal.arkansas.gov/service/ar-corp-bulk-data-download/)** — SOS online bulk (corps/LLC/LP/LLP…); CSV/XML; filter by type/status/agent (fees not listed on landing page)
- **[NY Open Data – Active Corporations](https://data.ny.gov/Economic-Development/Active-Corporations-Beginning-1800/n9v6-gdp6)** — free DOS entity extract (see [data-ny-gov.md](data-ny-gov.md)); Pierce had NY as “portal not observable”

**Limit:** “No bulk” ≠ brokers lack data; field coverage & cadence vary. DIY national file = stitch many states + buy/skip CA/DE gaps → why [GovFiles](govfiles.md)-class vendors exist. Use Pierce as map, then verify each state’s current fee page.
