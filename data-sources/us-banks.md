# US financial institutions (DIY federal / public)

Filename kept `us-banks.md`; scope = **banks + credit unions + brokers/securities firms** (and light BHC filings). Vendors: [fi-data-vendors.md](fi-data-vendors.md). Address cleanup: [address-usps.md](address-usps.md).

**Verdict:** Lists + branches + regulatory financials are **free DIY** by lane. Buy vendors only for unified schema, contacts, news, or global BIC/routing plants.

## Piecing order (recommended)

1. **Banks:** [FDIC Bank Data & Statistics](https://www.fdic.gov/analysis/bank-data-statistics) → BankFind Institutions + Locations + **SOD** + Bulk/API → join [FFIEC NIC](https://www.ffiec.gov/npw/FinancialReport/DataDownload) on CERT↔RSSD → call reports via CDR/UBPR.
2. **Credit unions:** [NCUA 5300 Call Report quarterly ZIPs](https://ncua.gov/analysis/credit-union-corporate-call-report-data/quarterly-data) (includes **Credit Union Branch Information** + financial schedules) ± CUOnline web service for aggregators.
3. **Brokers:** FINRA Developer Center **Broker Dealer Firm List** (+ BrokerCheck for diligence) + SEC EDGAR for public BD/BHC narrative.
4. **Hygiene:** Melissa (or peer) on all address fields — [address-usps.md](address-usps.md).

## Fields by lane

| Need | Banks (FDIC/FFIEC) | Credit unions (NCUA) | Brokers (FINRA/SEC) |
|------|--------------------|----------------------|---------------------|
| Legal name + IDs | CERT, RSSD, OCC # | Charter / CU # | CRD / SEC # |
| HQ address | Institutions / NIC Attributes | 5300 FOICU / profile tables | Firm registry / Form BD |
| Branch list | Locations; NIC Branches; **SOD** | 5300 branch table | Usually **not** SOD-like; offices via Form BD / vendor |
| Branch deposits | **SOD** (Jun 30) | Shares/deposits on 5300 (inst. grain; branch file = locations) | N/A |
| Balance sheet / P&L | Call Report (CDR); UBPR; FDIC Financial | Form **5300** schedules | FOCUS etc. (restricted); public cos → 10-K/10-Q |
| Parent / BHC | NIC Relationships; Y-9 | Corporate CU files; limited | Holding co via EDGAR / NIC if bank-affiliated |

## Banks — federal DIY detail

| Source | Gives | List? Branches? BS? |
|--------|-------|---------------------|
| [FDIC Bank Data & Statistics](https://www.fdic.gov/analysis/bank-data-statistics) | Hub: BankFind, SOD, CDR link, bulk/API, failures, annual summaries, deposit market share, Bank Data Guide | Start here |
| BankFind Institutions / Locations + API | Active/historical insured banks; office locations | Yes / Yes / via Financial endpoints |
| **SOD** | Branch deposits + addresses (annual) | Yes deposits |
| [FFIEC NIC Data Download](https://www.ffiec.gov/npw/FinancialReport/DataDownload) | Attributes Active/Closed/**Branches**; Relationships; Transformations (CSV/XML). Key `ID_RSSD`. (+ Y-9 HC financials on NIC) | Structure + branches; HC financials |
| [CDR Facsimiles](https://cdr.ffiec.gov/public/ManageFacsimiles.aspx) + PDD bulk | Call Reports / **UBPR** | Financials |
| [Fed LBR](https://www.federalreserve.gov/releases/lbr/current/) | Top commercial banks by assets | Partial list |
| [Chicago Fed commercial bank data](https://www.chicagofed.org/banking/financial-institution-reports/commercial-bank-data) | Legacy Call Report SAS 1976–2021; **frozen post-2021Q2** | Historical only → use CDR |
| [NY Fed banking research datasets](https://www.newyorkfed.org/research/banking_research/datasets) | CRSP–FRB link; 1867–1904 OCC BS; harmonized BS/IS ~1959–2025 | Research panels, not directory |
| OCC | National bank supervision / some lists; call data still via FFIEC | Supporting |
| SEC EDGAR / IR e.g. [USB filings](https://ir.usbank.com/financials/sec-filings/default.aspx) | **One BHC** narrative + consolidated GAAP | Pattern only — not universe |
| CFPB | Consumer complaints / HMDA-adjacent; **not** a bank directory | Skip for lists |

### Aggregates only (not directories)

| Source | Note |
|--------|------|
| [FRED DPSACBW027SBOG](https://fred.stlouisfed.org/series/DPSACBW027SBOG) | System-wide commercial bank deposits — charts |
| [SIFMA US Banks Quarterly](https://www.sifma.org/research/statistics/research-quarterly-us-banks) | CCAR cohort aggregates — deck |
| [data.gov Historical Bank Data](https://catalog.data.gov/dataset/historical-bank-data) | FDIC annual **industry** summary 1934–2019 — trends |

## Credit unions — NCUA

- [Call Report Data hub](https://ncua.gov/analysis/credit-union-corporate-call-report-data) + [quarterly ZIPs](https://ncua.gov/analysis/credit-union-corporate-call-report-data/quarterly-data): Form **5300** financials (1994+), **Credit Union Branch Information**, ATM locations, FOICU demographics.
- Custom Query UI; CUOnline web service (free but for serious bulk clients — register IP with NCUA).
- mapping.ncua.gov = consumer locator, not preferred bulk path.

## Brokers / securities

- **FINRA** [API Developer Center](https://developer.finra.org/catalog) — includes **Broker Dealer Firm List** dataset (registered BD firms); Public credential free with monthly download cap; Firm/Org credentials ~$1,650/mo. BrokerCheck UI for individuals/firms/disclosures; unofficial public JSON exists but prefer official catalog for production lists.
- **SEC EDGAR** — BD / holding company filings (10-K/10-Q; Form BD); IR pages e.g. USB are **one issuer**, not a universe.
- **Fed routing directory** (via FDIC hub) — ABA routing for payments, not a marketing directory.

## News / BD (bonus, minimal)

IR pages, EDGAR 8-K, FDIC/OCC/NCUA/FINRA enforcement & applications, light news alerts — separate from reference lists. Vendors often bundle news; DIY = alerts + IR.

## Related

- Commercial FI plants: [fi-data-vendors.md](fi-data-vendors.md)
- Address normalize: [address-usps.md](address-usps.md)
