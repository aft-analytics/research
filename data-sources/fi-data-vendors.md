# FI reference data vendors (banks / CUs / brokers)

Separate from federal DIY ([us-banks.md](us-banks.md)). Surveyed peers: BankFind alternatives → branch APIs → classic bank directories / risk terminals.

| Vendor | What | Can for lists/branches/stats? | Pricing signal | Fit |
|--------|------|-------------------------------|----------------|-----|
| **CREHQ** | Unified bank + CU branch API; geocode; change stream; builds on FDIC SOD + NCUA 5300 | Yes — enriched overlay on public regs | Contact-sales / quote | **Maybe** — buy if you don’t want to stitch DIY |
| **BankRegData** | Regulatory analytics / peer bank performance on call-report style data | Stats/peers more than raw directory | Contact-sales | **Maybe** for analytics UI |
| **S&P Global (Capital IQ / SNL)** | Institution profiles, financials, M&A, some branch | Yes enterprise | Contact-sales (expensive) | **Yes** if already licensed |
| **Moody’s / Orbis bank modules** | Credit + FI reference | Institution grain | Contact-sales | **Maybe** |
| **Accuity / LexisNexis Accuity** | Bank directory, payment KYC, sanctions-adjacent | Strong directory / BIC | Contact-sales | **Yes** for payments KYC directory |
| **SWIFTRef** | BIC / routing reference | IDs/routing, not US branch SOD | SWIFT membership / license | **Niche** — payments |
| **Bloomberg** | FI terminals / bank financials | Terminal users | Seat license | **Mild** unless already have |
| **Verilex / similar API wrappers** | Often thin wrap of FDIC + ABA/BIN | Can list; verify value-add | Varies / usage | Prefer raw FDIC unless DX needed |
| **FINRA API (Org credential)** | Official BD firm / branch / individual datasets | Firm list yes; not bank SOD | Public free (cap); Org/Firm **~$1,650/mo** | Prefer for brokers if volume needs official API |
| **Melissa** | Address verify (+ optional property) | **Not** an FI directory — hygiene only | Commercial (known to us) | **Yes** for address — [address-usps.md](address-usps.md) |

**Takeaway:** DIY FDIC+NCUA+FINRA covers US reference needs. Vendors win on **one schema**, contacts, global BIC, or analyst UI — not on exclusive US insured-bank facts.
