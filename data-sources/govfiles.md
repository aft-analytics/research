# GovFiles

[govfiles.dev](https://govfiles.dev/) · [docs](https://docs.govfiles.dev)

SOS entity registry product: claims **75M+** US entities (all 50 states), corps/LLCs/partnerships/nonprofits, active + dissolved, ~20y history, **monthly** refresh. Unified schema; officers/agents, name/status history, filings, FEIN/state IDs.

**Delivery:** REST API (lookup/search) or **bulk Parquet** (S3/SFTP; ~4.2 GB full 50-state drop cited) + Snowflake/BigQuery/Databricks shares.

**Pricing (site):** 1k rows/mo free, then **$0.01/row**; Scale **$499/mo** incl. 100k rows then **$0.004/row**; full-jurisdiction bulk = custom. Far more sane than CompanyData (~$30k/1M) for API use; national dump still needs a bulk quote.

**Source claim:** collected from each state’s SOS (not resellers). Verify sample coverage/freshness before relying on it.
