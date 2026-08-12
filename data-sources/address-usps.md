# Address standardization / USPS

**Melissa** ([melissa.com](https://www.melissa.com/) — Address Verification / Personator / Property): commercial path we already used. CASS/DPV-style standardize + verify; good for cleaning **bank / CU / broker HQ and branch** strings before matching txn text or geocoding. Also sells Property append (see [property-data-vendors.md](property-data-vendors.md)) — separate from address hygiene.

**USPS reality:** There is **no free national address dump**. Production move/hygiene products are licensed:
- **NCOA<sup>Link</sup>** / AIS — only via USPS-licensed full-service providers (or limited end-user licenses); not open data.
- USPS Web Tools / APIs — limited shipping/validate use cases; not a substitute for NCOA bulk.
- **Melissa** (and peers: Smarty, Lob, Experian, etc.) — one commercial path that wraps USPS-certified processes.

**For FI work:** FDIC / NCUA / FINRA give raw addresses → run Melissa (or peer) normalize → match. Move detection for fraud overlays → licensed NCOA path, not BankFind.
