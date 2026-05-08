# QuestDB (questdb)

QuestDB is a high-performance open-source time-series database used in trading, observability and IoT. It exposes three programmatic surfaces — an HTTP REST API for SQL and CSV import/export, the InfluxDB Line Protocol (ILP) over TCP and HTTP for ingestion, and the PostgreSQL wire protocol for compatibility with existing Postgres tooling.

**APIs.json:** [apis.yml](apis.yml)

## APIs
- **HTTP REST** — `http://<host>:9000` — `/exec` (SQL), `/imp` (CSV import), `/exp` (CSV export), `/chk`, `/metrics`, `/settings`. [Docs](https://questdb.com/docs/).
- **ILP TCP** — `tcp://<host>:9009` — high-throughput line-protocol ingestion. [Docs](https://questdb.com/docs/reference/api/ilp/overview/).
- **ILP HTTP** — `http://<host>:9000/write` — line-protocol over HTTP with TLS / auth.
- **PostgreSQL Wire** — `postgres://<host>:8812` — JDBC, psql and any Postgres client.

## OpenAPI
QuestDB does not currently publish a single OpenAPI document for its REST surface; pipeline did not retrieve a spec into `openapi/`.

## Tags
Database, Time-Series, SQL, Open Source, Performance, ILP, PostgreSQL

## Common Properties
- [Website](https://questdb.com/)
- [Documentation](https://questdb.com/docs/)
- [Enterprise](https://questdb.com/enterprise/)
- [BYOC](https://questdb.com/byoc/)
- [GitHub](https://github.com/questdb/questdb)
- [Plans](plans/questdb-plans-pricing.yml) — partially reconciled (editions; numeric prices private)
- [Rate Limits](rate-limits/questdb-rate-limits.yml) — operational defaults documented; numeric values are deployment-specific
- [FinOps](finops/questdb-finops.yml) — reconciled, FOCUS-aligned

## Editions (reconciled)
- **Open Source** — Apache 2.0; free.
- **Enterprise** — commercial self-hosted; HA, RBAC, RLS, tiered storage, audit, SLA. Custom pricing.
- **BYOC** — QuestDB-managed in your AWS / Azure account (GCP planned). Custom pricing.
- **AWS Marketplace** — private offers via marketplace@questdb.io.

## Notes
The fully-managed QuestDB Cloud SaaS has been retired; the managed offering is now BYOC + Enterprise.

## Timestamps
- **Created:** 2026-05-08
- **Modified:** 2026-05-08

## Maintainers
- **Kin Lane** — kin@apievangelist.com
