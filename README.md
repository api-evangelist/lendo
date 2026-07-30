# Lendo

Lendo (شركة ليندو السعودية للتمويل) is a Riyadh-based Saudi fintech licensed by the Saudi Central Bank (SAMA, License No. 61/A SH/202203) operating the Kingdom's first SAMA-licensed Sharia-compliant debt-based crowdfunding platform, connecting SMEs needing liquidity with retail and institutional investors through invoice financing, working capital financing, purchase-order financing and government-backed programs.

Website: https://lendo.sa — Backed by: 500-global

## API posture

Lendo publishes **no public developer program** — no developer portal, API reference, OpenAPI definition, SDKs, CLI, GitHub organization, webhooks or partner integration documentation.

What the enrichment pipeline did find:

- **`llms/lendo-llms.txt`** — a real `llms.txt` published at https://lendo.sa/llms.txt, captured verbatim.
- **`api.lendo.sa`** — a live production API host backing the web and mobile apps. Every path returns 401/403 without a bearer token. Its `/v3/api-docs` route answers *"Forbidden: This endpoint is not available in production"*, confirming a springdoc-openapi definition that exists internally but is not exposed.
- **`security/lendo-trust-center.yml`** — a SafeBase-hosted trust center at https://trust.lendo.sa/ naming SAMA CSF as its compliance framework (no SOC 2 / ISO 27001 / PCI DSS listed).
- **`conventions/` + `errors/`** — request/response semantics and the proprietary bilingual `{message, status, responseTimestamp}` error envelope, recorded from live probes rather than documentation.
- **`security/lendo-domain-security.yml`** — TLS 1.3 and HSTS across all hosts; no DNSSEC, no CAA; SPF and DMARC (quarantine) present.
- **`well-known/`** — no `/.well-known/` discovery documents published; no `security.txt`, and no vulnerability disclosure programme anywhere on the site (the `/report-violation` page is fraud/ethics reporting, not security).
