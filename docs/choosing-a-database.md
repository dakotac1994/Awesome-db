# Choosing a database

A practical guide to picking from the [Awesome-db](../README.md) catalog. The short version: **match the data model to the access pattern, then check the license.**

## 1. What does your workload look like?

| Workload | You need | Look at |
| --- | --- | --- |
| App records, transactions, "the money moved exactly once" | ACID, joins, strong consistency | [Relational](../README.md#relational) |
| Relational data too big for one machine | SQL + horizontal scale + strong consistency | [Distributed SQL](../README.md#distributed-sql) |
| Flexible JSON records, evolving schemas | Document model, secondary indexes | [Document](../README.md#document) |
| Cache, sessions, counters, leaderboards, queues | Sub-millisecond KV ops | [Key-Value](../README.md#key-value) |
| Massive write throughput, sparse wide rows | Partition-tolerant wide rows | [Wide-Column](../README.md#wide-column) |
| Fraud rings, recommendations, knowledge graphs, "friends of friends" | Traversals, not joins | [Graph](../README.md#graph) |
| Metrics, IoT, market ticks, observability | High-ingest timestamps, retention, downsampling | [Time-Series](../README.md#time-series) |
| Semantic search, RAG, recommendations over embeddings | ANN vector search | [Vector](../README.md#vector) |
| Product search, site search, log search with relevance ranking | Full-text + filters | [Search](../README.md#search) |
| Dashboards, reporting, ad-hoc analytics over large data | Columnar scans, aggregations | [OLAP & Analytical](../README.md#olap--analytical) |

## 2. OLTP vs OLAP vs both

- **OLTP** (many small transactions): relational, distributed SQL, key-value, document.
- **OLAP** (few big analytical queries): the OLAP section — columnar engines.
- **Both (HTAP):** TiDB and SingleStore claim it; in practice most teams still run an OLTP primary plus an OLAP replica/warehouse.

## 3. Consistency: how much can you relax?

- Need linearizable/serializable guarantees across nodes → consensus-based systems: CockroachDB, YugabyteDB, TiDB, etcd, FoundationDB.
- Eventual consistency is fine (feeds, carts, counters) → Cassandra/ScyllaDB, Dynamo-style KV, many document stores.
- Single-node engines (PostgreSQL, SQLite, DuckDB) sidestep the question entirely — and are shockingly far along the "just use Postgres" curve.

## 4. The license check (do this before you commit)

This space relicenses often. Before building on an engine:

1. Read the actual LICENSE file, not the marketing page. This list's `license` field is copied from it.
2. Know what non-OSI means for you: **SSPL** and **BSL** restrict offering the software as a competing service; **proprietary** means a vendor contract.
3. If you need a Redis-protocol drop-in under a permissive license, that's Valkey (BSD-3-Clause), not Redis.
4. If you need Elasticsearch-compatible search under Apache-2.0, that's OpenSearch.

Notable relicensing events are logged in [status-changes](status-changes.md).

## 5. Operational reality

- **Single binary, zero ops:** SQLite, DuckDB, etcd (small clusters), Meilisearch, Typesense, QuestDB.
- **Serious distributed ops:** Cassandra/ScyllaDB, HBase, Elasticsearch/OpenSearch clusters, TiDB, CockroachDB — budget for expertise or a managed offering.
- **Embedded in your app:** SQLite, DuckDB, RocksDB, PouchDB, Realm — no server to run at all.

## 6. Quick picks by scenario

- New SaaS backend, uncertain scale → PostgreSQL.
- Analytics sidecar next to your app → DuckDB.
- Cache/session layer → Valkey.
- Semantic search for an AI feature → pgvector if you're already on Postgres; Qdrant/Milvus for dedicated scale.
- Metrics pipeline → Prometheus or VictoriaMetrics; high-cardinality IoT → QuestDB or InfluxDB.
- Product search box → Meilisearch or Typesense for simplicity; OpenSearch/Elasticsearch for scale and ecosystem.
