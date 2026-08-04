# Lendo

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
