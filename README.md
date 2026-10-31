# QuestDB

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

**Areas:** Database · Time Series · SQL · Open Source · Performance · ILP · PostgreSQL

## QuestDB on APIs.io

Everything profiled for QuestDB is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/questdb/](https://apis.io/providers/questdb/)** — or go straight to one of the APIs or properties below.

### APIs (10)

- [QuestDB HTTP REST API](https://apis.io/apis/questdb/rest-http/) — HTTP REST endpoints for SQL execution (/exec), CSV import (/imp), CSV export (/exp), health/metrics (/chk, /metrics) and runtime settings (/settings).…
- [QuestDB ILP TCP Ingestion](https://apis.io/apis/questdb/ilp-tcp/) — InfluxDB Line Protocol over TCP for high-throughput, low-latency time-series ingestion. Default port 9009. Supports authentication and TLS in Enterprise.
- [QuestDB ILP HTTP Ingestion](https://apis.io/apis/questdb/ilp-http/) — Influx Line Protocol over HTTP /write endpoint for ingestion clients that prefer HTTP (TLS, auth and ack semantics easier than the TCP variant). Served on…
- [QuestDB PostgreSQL Wire Interface](https://apis.io/apis/questdb/postgres-wire/) — PostgreSQL wire-protocol compatibility for queries via psql, JDBC and any Postgres-compatible client. Default port 8812. Supports a subset of Postgres…
- [QuestDB Chk API](https://apis.io/apis/questdb/questdb-chk-api/) — The Chk API from QuestDB — 1 operation(s) for chk.
- [QuestDB Exec API](https://apis.io/apis/questdb/questdb-exec-api/) — The Exec API from QuestDB — 1 operation(s) for exec.
- [QuestDB Exp API](https://apis.io/apis/questdb/questdb-exp-api/) — The Exp API from QuestDB — 1 operation(s) for exp.
- [QuestDB Imp API](https://apis.io/apis/questdb/questdb-imp-api/) — The Imp API from QuestDB — 1 operation(s) for imp.
- [QuestDB Settings API](https://apis.io/apis/questdb/questdb-settings-api/) — The Settings API from QuestDB — 1 operation(s) for settings.
- [QuestDB Write API](https://apis.io/apis/questdb/questdb-write-api/) — The Write API from QuestDB — 1 operation(s) for write.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Questdb Agentic Access](https://apis.io/agentic-access/questdb/questdb-agentic-access/)

#### Collections (7)

Postman and Open Collection request collections.

- [QuestDB HTTP REST API](https://apis.io/collections/questdb/open-questdb/)
- [QuestDB HTTP REST Chk API](https://apis.io/collections/questdb/open-questdb-chk-api/)
- [QuestDB HTTP REST Chk Exec API](https://apis.io/collections/questdb/open-questdb-exec-api/)
- [QuestDB HTTP REST Chk Exp API](https://apis.io/collections/questdb/open-questdb-exp-api/)
- [QuestDB HTTP REST Chk Imp API](https://apis.io/collections/questdb/open-questdb-imp-api/)
- [QuestDB HTTP REST Chk Settings API](https://apis.io/collections/questdb/open-questdb-settings-api/)
- [QuestDB HTTP REST Chk Write API](https://apis.io/collections/questdb/open-questdb-write-api/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Questdb Authentication](https://apis.io/security/questdb/questdb-authentication/)
- [Questdb Domain Security](https://apis.io/security/questdb/questdb-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Questdb Plans Pricing](https://apis.io/plans/questdb/questdb-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Questdb Rate Limits](https://apis.io/rate-limits/questdb/questdb-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Questdb Finops](https://apis.io/finops/questdb/questdb-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://questdb.com/)
- [Documentation](https://questdb.com/docs/)
- [Pricing](https://questdb.com/enterprise/)
- [Blog](https://questdb.com/rss.xml)

## API Evangelist rating

**Kin Score 30.7** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 47.6 |
| Contract governance | 0.0 |
| Operational transparency | 13.2 |
| Developer ergonomics | 31.0 |
| Access clarity | 18.4 |

**Agent readiness 17.9** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 11.8** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/questdb/](https://apis.io/providers/questdb/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for QuestDB: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/questdb/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
