# Property / deed data vendors (vs ATTOM)

Minimal can/cannot pass for **national ownership / assessor / deed overlays**. Snowball: ATTOM → CoreLogic/DataTree/Black Knight → Zillow/BatchData/Estated → Regrid/RentCast/HouseCanary/Melissa/LightBox/RealEstateAPI/TovoData. Stopped when new names were mostly consumer people-search, tax-lien tools, or aggregators.

**Different lane (not plant peers):** [U.S. Title Records](us-title-records.md) and AFX Research — per-order human abstractors / title reports (API = order status + PDF, not bulk ownership files). FastLien = tax-lien auction SaaS ($49/mo) — skip for ownership overlays.

| Vendor | What it is | Grain / coverage claim | Delivery | Pricing signal | Fit for ownership overlays |
|--------|------------|------------------------|----------|----------------|----------------------------|
| **ATTOM** (baseline; Estated now part of ATTOM) | Assessor + recorder/deed + mortgage/foreclosure plant | ~158–160M US props; recorder ~2.7k+ counties / 500M+ txns claimed | REST API (30-day trial); bulk; Snowflake/Databricks Delta Share (recorder deeds in share catalog) | Contact-sales (API by “reports”); Navigator ~$499/yr list; trial free | **Yes** — primary peer class for match-append ownership |
| **Cotality (CoreLogic)** | Deepest institutional property + analytics; CLIP ID | ~99.9% US props claimed | Enterprise API / Araya / cloud (Databricks, Snowflake, GCP); Trestle more MLS | Contact-sales | **Yes** — enterprise plant; heavier procurement |
| **First American DataTree** | Title-grade ownership + recorded doc images (~6–7B images claimed) | Nationwide parcels / deeds | Web UI + API + bulk | Contact-sales | **Yes** — strongest doc-image / title path |
| **ICE / Black Knight** | Mortgage + collateral + property/lien stack | Lender/servicer-centric | Enterprise only | Contact-sales | **Maybe** — great if mortgage-linked; not self-serve prop plant |
| **BatchData** | Prop + owner contact / skip-trace oriented | ~155M props claimed | REST + Snowflake/S3/bulk | Public tiers from **$1k/mo** (100k records) | **Yes** — usable self-serve for owner fields; marketing skew |
| **Regrid** | Parcel GIS + ownership / zoning | ~160M parcels; 100% US parcel claim | Self-serve REST + batch + MCP | Self-serve monthly; enterprise >10k/mo | **Yes** — ownership + geometry; lighter deed history than ATTOM |
| **Melissa Property** | Property/mortgage append (~400 fields); also **address verify** (separate product) | ~150M props; county-sourced | Property API + batch append; Address Verification | Contact-sales / demo | **Yes** property append; address hygiene → [address-usps.md](address-usps.md) |
| **RentCast** | Prop records + owner + AVM/listings/rent | ~150M props | Self-serve REST | **$0–449/mo** + overage ($0.015–0.20/req); 50 free calls | **Maybe** — owner present; thinner title plant than ATTOM |
| **RealEstateAPI.com** | Dev-focused public-records aggregation | National (vendor claim) | REST + bulk | Starter cited **~$599/mo** | **Maybe** — quote + sample quality |
| **TovoData** | Credit-metered prop/owner/lien API | ~150M props claimed | REST (Swagger) | Credits **$50–2,500** packs ($0.25–0.50/credit) | **Maybe** — cheap trial; verify depth vs plant |
| **Homesage.ai** | AI investor metrics on prop base | ~155M props claimed | REST (30+ endpoints) | Credits; plans **~$200–1,000/mo** | **Maybe** — analytics-first; ownership secondary |
| **HouseCanary** | AVM / forecast / risk | ~136M+ props claimed | REST + cloud | Contact-sales / enterprise | **Mild** — valuation, not deed plant |
| **LightBox** | CRE property intelligence + LightBox ID | Commercial-focused nationwide | API + bulk feed | Contact-sales | **Maybe** — CRE; not consumer-lending default |
| **Zillow Data** | Zestimate / research / Bridge; ZTRAX for research | Listings + some public records | Research CSV free; commercial API/Bridge approval | Free research; commercial contact/approval | **Mild** — not redistributable plant for book overlays |
| **Dwellsy IQ** | Unit-level **rental** comps from PMS | ~17M listings (rental), not deed plant | API + cloud | Contact-sales | **No** for ownership — rental lane |
| **Estated** | Former clean prop API | Folded into ATTOM | → ATTOM API | → ATTOM | Use **ATTOM**; do not dual-source |

**Takeaway:** Closest ATTOM peers for **ownership verification overlays** = **DataTree**, **Cotality/CoreLogic**, then **BatchData / Regrid / Melissa** if you want faster self-serve. Abstractors (USTR, AFX) = exception path only. See also [deeds-by-state.md](deeds-by-state.md) for DIY county framing.
