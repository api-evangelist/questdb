# QuestDB (questdb)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

QuestDB is a high-performance open-source time-series database. It exposes three programmatic surfaces — an HTTP REST API for SQL queries and CSV import/export, the InfluxDB Line Protocol (ILP) over TCP and HTTP for high-throughput ingestion, and the PostgreSQL wire protocol for compatibility with existing tooling. QuestDB is offered as open-source, Enterprise (self-hosted) and Bring-Your-Own-Cloud (BYOC).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/questdb/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/questdb/refs/heads/main/apis.yml)

## Tags

- Database
- Time-Series
- SQL
- Open Source
- Performance
- ILP
- PostgreSQL

## Timestamps

- **Created:** 2026-05-08
- **Modified:** 2026-05-08

## APIs

### QuestDB HTTP REST API

HTTP REST endpoints for SQL execution (/exec), CSV import (/imp), CSV export (/exp), health/metrics (/chk, /metrics) and runtime settings (/settings). Default port 9000.

- **Human URL:** [https://questdb.com/docs/reference/sql/overview/](https://questdb.com/docs/reference/sql/overview/)
- **Base URL:** `http://<host>:9000`

#### Tags

- REST
- SQL
- CSV
- Health
- Metrics

#### Properties

- [Documentation](https://questdb.com/docs/)
- [API Reference](https://questdb.com/docs/reference/api/rest/)
- [Postman Collection](collections/questdb.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/questdb.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### QuestDB ILP TCP Ingestion

InfluxDB Line Protocol over TCP for high-throughput, low-latency time-series ingestion. Default port 9009. Supports authentication and TLS in Enterprise.

- **Human URL:** [https://questdb.com/docs/reference/api/ilp/overview/](https://questdb.com/docs/reference/api/ilp/overview/)
- **Base URL:** `tcp://<host>:9009`

#### Tags

- ILP
- TCP
- Ingestion

#### Properties

- [Documentation](https://questdb.com/docs/reference/api/ilp/overview/)
- [Postman Collection](collections/questdb.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/questdb.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### QuestDB ILP HTTP Ingestion

Influx Line Protocol over HTTP /write endpoint for ingestion clients that prefer HTTP (TLS, auth and ack semantics easier than the TCP variant). Served on the same port (9000) as the REST API.

- **Human URL:** [https://questdb.com/docs/reference/api/ilp/overview/](https://questdb.com/docs/reference/api/ilp/overview/)
- **Base URL:** `http://<host>:9000`

#### Tags

- ILP
- HTTP
- Ingestion

#### Properties

- [Postman Collection](collections/questdb.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/questdb.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### QuestDB PostgreSQL Wire Interface

PostgreSQL wire-protocol compatibility for queries via psql, JDBC and any Postgres-compatible client. Default port 8812. Supports a subset of Postgres features sufficient for SQL analytics on QuestDB.

- **Human URL:** [https://questdb.com/docs/develop/connect/](https://questdb.com/docs/develop/connect/)
- **Base URL:** `postgres://<host>:8812`

#### Tags

- PostgreSQL
- Wire Protocol
- JDBC

#### Properties

- [Postman Collection](collections/questdb.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/questdb.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/questdb)
- [Website](https://questdb.com/)
- [Documentation](https://questdb.com/docs/)
- [Pricing](https://questdb.com/enterprise/)
- [Git Hub](https://github.com/questdb/questdb)
- [B Y O C](https://questdb.com/byoc/)
- [Plans](plans/questdb-plans-pricing.yml)
- [Rate Limits](rate-limits/questdb-rate-limits.yml)
- [Fin Ops](finops/questdb-finops.yml)
- [L L Ms Txt](https://questdb.com/llms.txt)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
