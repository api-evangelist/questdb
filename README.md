# QuestDB (questdb)

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
