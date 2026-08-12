# Address standardization / USPS

**Melissa** ([melissa.com](https://www.melissa.com/) — Address Verification / Personator / Property): commercial path we already used. CASS/DPV-style standardize + verify; good for cleaning **bank / CU / broker HQ and branch** strings before matching txn text or geocoding. Also sells Property append (see [property-data-vendors.md](property-data-vendors.md)) — separate from address hygiene.

**USPS reality:** There is **no free national address dump**. Production move/hygiene products are licensed:
- **NCOA<sup>Link</sup>** / AIS — only via USPS-licensed providers; not open data (detail below).
- USPS Web Tools / APIs — limited shipping/validate use cases; not a substitute for NCOA bulk.
- **Melissa** (and peers: Smarty, Lob, Experian, etc.) — one commercial path that wraps USPS-certified processes.

**For FI work:** FDIC / NCUA / FINRA give raw addresses → run Melissa (or peer) normalize → match. Move detection for fraud overlays → licensed NCOA path, not BankFind.

## NCOA<sup>Link</sup> (deeper)

Hub: [PostalPro NCOALink](https://postalpro.usps.com/mailing-and-shipping-services/ncoalink) — official licensee lists + docs.

| Fact | Detail |
|------|--------|
| What it is | USPS COA file matched to **your** name/address list (mailer Move Update / list hygiene) |
| DIY dump? | **No** — cannot download the national COA database |
| How to buy | Through USPS-licensed **Full Service** (48 mo COA) or **Limited Service** (18 mo) providers; or End User / Intermediate licenses if we process in-house |
| Friction | Customer signs **PAF** (Processing Acknowledgement Form); CASS-certified matching; weekly licensee updates from USPS |
| Fraud / instability signal | “Moved” / new address on book accounts — useful overlay, but **licensed batch**, not a continuous free feed |
| Path for us | Keep Melissa (or peer NCOA reseller) for hygiene + moves; don’t plan a free NCOA scrape |

**Verdict:** Yes for move/fraud overlays **only via licensed vendor**. Address-usps.md is the home note; no separate open dataset exists.
