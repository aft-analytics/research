# Data USA

[datausa.io](https://datausa.io/) · API: [api.datausa.io](https://api.datausa.io/) · [about/api (Data)](https://datausa.io/about/api) · GitHub [DataUSA](https://github.com/DataUSA)

Deloitte + Datawheel (+ MIT Media Lab origins) **viz/API layer** over public US government stats. ~47k auto-generated reports on places, industries, jobs, universities, degrees. Chart download + API (Tesseract/Cube).

**Sources underneath:** ACS and other federal series (ETL repos e.g. `datausa-acs-etl`) — same family as [Census](census.md), not new microdata.

**Useful for:** quick place/industry/occupation overlays, talent/market slides.  
**Not useful for:** SOS entities, deeds, permits, NFIP microdata, borrower-level features.

Prefer Census/BLS primary files when building production features; Data USA is a convenience front end.
