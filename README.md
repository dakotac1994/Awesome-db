# Awesome DB

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Entries](https://img.shields.io/badge/entries-73-blue)](data/databases.json)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

A curated list of **database engines and systems**, organized by data model: relational, distributed SQL, document, key-value, wide-column, graph, time-series, vector, search, and OLAP/analytical engines.

> **Scope:** this list covers *database engines* — the software that stores and queries data. Database GUI clients (DBeaver, DataGrip, TablePlus), ORMs (Prisma, SQLAlchemy), migration tools (Flyway, Liquibase), and managed-DBaaS-only wrappers with no self-hostable engine (PlanetScale, Neon, Pinecone) are out of scope.
> **Honesty policy:** every entry was checked against an official source (project repo, LICENSE file, or official site) as of 2026-09-30 — **73/73 verified**. Unverified entries carry a stated reason. This space relicenses often: non-OSI licenses (SSPL, BSL, source-available, proprietary) are labeled exactly as the project's LICENSE file states, never softened to "open source". Machine-readable data lives in [`data/databases.json`](data/databases.json).

## Contents

- [Relational](#relational) — 9 entries
- [Distributed SQL](#distributed-sql) — 8 entries
- [Document](#document) — 8 entries
- [Key-Value](#key-value) — 9 entries
- [Wide-Column](#wide-column) — 3 entries
- [Graph](#graph) — 7 entries
- [Time-Series](#time-series) — 7 entries
- [Vector](#vector) — 8 entries
- [Search](#search) — 6 entries
- [OLAP & Analytical](#olap--analytical) — 8 entries

## Choosing the right database

New here? Start with the [choosing-a-database](docs/choosing-a-database.md) guide (OLTP vs OLAP, consistency needs, the license check), the [glossary](docs/glossary.md), and [status-changes](docs/status-changes.md) (relicensing events, renames, shutdowns).

## Relational

The workhorses: ACID transactions, joins, and SQL standards compliance — from the embedded SQLite to Oracle Database. (9 entries)

- [Firebird](https://firebirdsql.org) — Open-source relational database derived from Borland InterBase, under the IDPL license. *(IDPL-1.0 · ⭐ 1,472)*
- [H2](https://www.h2database.com) — Java SQL database supporting embedded, server, and in-memory modes. *(MPL-2.0 OR EPL-1.0 · ⭐ 4,634)*
- [libSQL](https://libsql.org) — SQLite fork by Turso for the edge, adding replication and sync from edge replicas. *(MIT · ⭐ 17,247)*
- [MariaDB](https://mariadb.org) — Community-developed fork of MySQL maintaining protocol and API compatibility. *(GPL-2.0-only · ⭐ 8,306)*
- [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server) — Proprietary relational database from Microsoft, the flagship T-SQL engine. *(proprietary)*
- [MySQL](https://www.mysql.com) — Widely deployed open-source relational database, the community edition is GPL-licensed. *(GPL-2.0-only · ⭐ 12,436)*
- [Oracle Database](https://www.oracle.com/database/) — Proprietary multi-model relational database management system from Oracle. *(proprietary)*
- [PostgreSQL](https://www.postgresql.org) — Advanced open-source object-relational database with strong standards compliance and extensibility. *(PostgreSQL · ⭐ 22,250)*
- [SQLite](https://www.sqlite.org) — Self-contained, serverless, zero-configuration SQL database engine in a single C library. *(public domain)*

## Distributed SQL

SQL with horizontal scale: sharded, consensus-backed relational engines for workloads that outgrow a single node. (8 entries)

- [Citus](https://www.citusdata.com) — PostgreSQL extension (AGPL) that turns Postgres into a distributed database. *(AGPL-3.0-only · ⭐ 12,796)*
- [CockroachDB](https://www.cockroachdb.com) — Distributed SQL database with strong consistency, Postgres-compatible wire protocol. *(proprietary · ⭐ 32,539)*
- [FoundationDB](https://www.foundationdb.org) — Ordered key-value store with strict serializable transactions, basis for SQL layers. *(Apache-2.0 · ⭐ 16,744)*
- [Google Cloud Spanner](https://cloud.google.com/spanner) — Google's proprietary globally distributed relational database with external consistency. *(proprietary)*
- [SingleStore](https://www.singlestore.com) — Proprietary distributed SQL database for operational analytics and real-time workloads. *(proprietary)*
- [TiDB](https://tidb.io) — Distributed SQL database with MySQL compatibility and HTAP workloads support. *(Apache-2.0 · ⭐ 40,615)*
- [Vitess](https://vitess.io) — Database clustering system for horizontal scaling of MySQL (powers YouTube's data layer). *(Apache-2.0 · ⭐ 21,362)*
- [YugabyteDB](https://www.yugabyte.com) — Distributed SQL database with Postgres (YSQL) and Cassandra (YCQL) compatible APIs. *(Apache-2.0 · ⭐ 10,568)*

## Document

Flexible JSON-like documents with secondary indexes — for evolving schemas and developer velocity. (8 entries)

- [Apache CouchDB](https://couchdb.apache.org) — Distributed JSON document store with MVCC and MapReduce views, replicated over HTTP. *(Apache-2.0 · ⭐ 6,967)*
- [Couchbase Server](https://www.couchbase.com) — Multi-model distributed database with JSON documents, key-value access and SQL++ querying. *(BSL-1.1 · ⭐ 233)*
- [FerretDB](https://www.ferretdb.com) — Drop-in MongoDB-protocol replacement that stores documents in PostgreSQL or SQLite backends. *(Apache-2.0 · ⭐ 11,089)*
- [LiteDB](https://www.litedb.org) — Serverless embedded .NET document database in a single DLL file. *(MIT · ⭐ 9,481)*
- [Marten](https://martendb.io) — .NET transactional document database and event store built on PostgreSQL. *(MIT · ⭐ 3,458)*
- [MongoDB](https://www.mongodb.com) — Distributed JSON document database with a query API and aggregation pipelines. *(SSPL-1.0 · ⭐ 28,613)*
- [PocketBase](https://pocketbase.io) — Single-file embedded backend combining document database, realtime APIs, auth and file storage. *(MIT · ⭐ 61,221)*
- [RavenDB](https://ravendb.net) — Distributed NoSQL document database with ACID transactions and a built-in management studio. *(AGPL-3.0-only · ⭐ 4,002)*

## Key-Value

The speed layer: sub-millisecond reads and writes by key, from in-memory caches to embedded LSM stores. (9 entries)

- [BadgerDB](https://dgraph.io) — Embeddable persistent key-value store for Go with LSM trees and ACID transactions. *(Apache-2.0 · ⭐ 15,780)*
- [Dragonfly](https://www.dragonflydb.io) — Multi-threaded Redis/Memcached-compatible in-memory store with snapshotting to disk. *(BSL-1.1 · ⭐ 31,729)*
- [etcd](https://etcd.io) — Distributed reliable key-value store used for service discovery and cluster coordination. *(Apache-2.0 · ⭐ 52,328)*
- [KeyDB](https://keydb.dev) — Multi-threaded Redis fork with active replication and flash (SSD-backed) storage support. *(BSD-3-Clause · ⭐ 12,508)*
- [LevelDB](https://github.com/google/leveldb) — Fast embedded key-value storage library written at Google. *(BSD-3-Clause · ⭐ 39,460)*
- [Redis](https://redis.io) — In-memory data structure store with persistence, used as cache, database and message broker. *(AGPL-3.0-only · ⭐ 76,562)*
- [RocksDB](https://rocksdb.org) — Embedded persistent key-value store based on a log-structured merge-tree. *(Apache-2.0 AND GPL-2.0 · ⭐ 32,157)*
- [TiKV](https://tikv.org) — Distributed transactional key-value database powering TiDB clusters. *(Apache-2.0 · ⭐ 16,890)*
- [Valkey](https://valkey.io) — Linux Foundation fork of Redis, multi-threaded and protocol-compatible with Redis clients. *(BSD-3-Clause · ⭐ 27,348)*

## Wide-Column

Sparse, massively scalable two-dimensional keyspaces for write-heavy workloads across commodity clusters. (3 entries)

- [Apache Cassandra](https://cassandra.apache.org) — Distributed wide-column store for large-scale workloads across commodity servers. *(Apache-2.0 · ⭐ 10,111)*
- [Apache HBase](https://hbase.apache.org) — Hadoop-based distributed wide-column store modeled after Google Bigtable. *(Apache-2.0 · ⭐ 5,562)*
- [ScyllaDB](https://www.scylladb.com) — High-performance C++ rewrite of Cassandra with shard-per-core architecture. *(ScyllaDB-Source-Available · ⭐ 15,782)*

## Graph

Nodes, edges, and traversals as first-class citizens — for connected data that joins can't reach. (7 entries)

- [ArangoDB](https://arangodb.com) — Multi-model database for graphs, documents, and key-values with the AQL query language. *(BSL-1.1 · ⭐ 14,280)*
- [Dgraph](https://dgraph.io) — Distributed native graph database with GraphQL+- and GraphQL query support. *(Apache-2.0 · ⭐ 21,804)*
- [JanusGraph](https://janusgraph.org) — Distributed graph database over pluggable storage backends, queried with Gremlin. *(Apache-2.0 · ⭐ 5,840)*
- [Kuzu](https://kuzudb.com) — Embedded graph database with Cypher, built for analytical query speed and scalability. *(MIT · ⭐ 4,024)*
- [Memgraph](https://memgraph.com) — In-memory graph database with Cypher support for real-time analytics. *(BSL-1.1 · ⭐ 4,586)*
- [Neo4j](https://neo4j.com) — Property graph database queried with Cypher; the most widely deployed graph DBMS. *(GPL-3.0-only · ⭐ 17,269)*
- [OrientDB](https://orientdb.dev) — Multi-model database combining graph, document, and object stores with SQL support. *(Apache-2.0 · ⭐ 4,991)*

## Time-Series

Timestamped measurements at high ingest: retention policies, downsampling, and PromQL/SQL querying. (7 entries)

- [Apache IoTDB](https://iotdb.apache.org) — Time-series database built for industrial IoT and edge data at scale. *(Apache-2.0 · ⭐ 6,404)*
- [GridDB](https://griddb.net) — In-memory NoSQL database for time-series IoT and big data workloads. *(AGPL-3.0-only · ⭐ 2,473)*
- [InfluxDB](https://www.influxdata.com) — Time-series database with SQL and InfluxQL for metrics, events, and real-time analytics. *(MIT / Apache-2.0 · ⭐ 31,760)*
- [Prometheus](https://prometheus.io) — Monitoring system and time-series database with the PromQL query language. *(Apache-2.0 · ⭐ 66,330)*
- [QuestDB](https://questdb.com) — High-performance SQL time-series database for market data and sensor workloads. *(Apache-2.0 · ⭐ 17,402)*
- [TimescaleDB](https://www.timescale.com) — PostgreSQL extension for time-series with hypertables and continuous aggregates. *(Apache-2.0 + Timescale License · ⭐ 23,629)*
- [VictoriaMetrics](https://victoriametrics.com) — Fast, resource-efficient time-series database and monitoring solution. *(Apache-2.0 · ⭐ 17,795)*

## Vector

Embeddings and approximate nearest-neighbor search — the database layer for semantic and AI search. (8 entries)

- [Chroma](https://www.trychroma.com) — Embeddable open-source vector database for AI applications and RAG. *(Apache-2.0 · ⭐ 29,417)*
- [LanceDB](https://lancedb.com) — Developer-friendly serverless vector database built on the Lance columnar format. *(Apache-2.0 · ⭐ 11,566)*
- [Milvus](https://milvus.io) — Distributed vector database for billion-scale similarity search. *(Apache-2.0 · ⭐ 46,293)*
- [pgvector](https://github.com/pgvector/pgvector) — Open-source vector similarity search extension for PostgreSQL. *(PostgreSQL License · ⭐ 23,202)*
- [Qdrant](https://qdrant.tech) — Vector search engine for high-performance similarity search with payload filtering. *(Apache-2.0 · ⭐ 34,892)*
- [Vald](https://vald.vdaas.org) — Cloud-native distributed vector search engine designed for Kubernetes. *(Apache-2.0 · ⭐ 1,733)*
- [Vespa](https://vespa.ai) — Big-data serving engine for search, recommendations, and RAG at scale. *(Apache-2.0 · ⭐ 7,114)*
- [Weaviate](https://weaviate.io) — Vector database with hybrid search and built-in ML modules for AI applications. *(BSD-3-Clause + Weaviate License · ⭐ 16,859)*

## Search

Full-text search with relevance ranking over JSON documents, logs, and product catalogs. (6 entries)

- [Apache Solr](https://solr.apache.org) — Enterprise search platform built on Apache Lucene. *(Apache-2.0 · ⭐ 1,678)*
- [Elasticsearch](https://www.elastic.co/elasticsearch) — Distributed search and analytics engine over JSON documents. *(AGPL-3.0-only / SSPL-1.0 / Elastic License 2.0 · ⭐ 78,163)*
- [Meilisearch](https://www.meilisearch.com) — Fast, typo-tolerant search engine with instant results and a REST API. *(MIT + BSL-1.1 · ⭐ 59,447)*
- [OpenSearch](https://opensearch.org) — Community-driven search and analytics suite forked from Elasticsearch. *(Apache-2.0 · ⭐ 13,796)*
- [Tantivy](https://github.com/quickwit-oss/tantivy) — Full-text search engine library for Rust, inspired by Apache Lucene. *(MIT · ⭐ 16,162)*
- [Typesense](https://typesense.org) — Typo-tolerant search engine with a simple HTTP API and instant search UX. *(GPL-3.0-only · ⭐ 26,616)*

## OLAP & Analytical

Columnar engines for scans and aggregations over large datasets — dashboards, reporting, ad-hoc analytics. (8 entries)

- [Apache Doris](https://doris.apache.org) — Apache MPP analytical database for real-time analytics on large datasets. *(Apache-2.0 · ⭐ 16,020)*
- [Apache Druid](https://druid.apache.org) — Apache real-time analytics database for slicing and dicing large datasets. *(Apache-2.0 · ⭐ 14,058)*
- [Apache Pinot](https://pinot.apache.org) — Apache real-time OLAP datastore for ultra-low-latency analytics at scale. *(Apache-2.0 · ⭐ 6,146)*
- [ClickHouse](https://clickhouse.com) — Open-source column-oriented DBMS for real-time analytical queries. *(Apache-2.0 · ⭐ 50,171)*
- [DuckDB](https://duckdb.org) — In-process analytical SQL database engine with a focus on ease of use and performance. *(MIT · ⭐ 41,837)*
- [Google BigQuery](https://cloud.google.com/bigquery) — Google's proprietary serverless data warehouse for petabyte-scale analytics. *(proprietary)*
- [Snowflake](https://www.snowflake.com) — Proprietary cloud data platform with a shared-nothing MPP analytical engine. *(proprietary)*
- [StarRocks](https://www.starrocks.io) — MPP analytical database for real-time reporting, forked from Apache Doris. *(Apache-2.0 · ⭐ 12,150)*

## Notable exclusions

Candidates that were researched and deliberately left out:

| Excluded | Reason |
| --- | --- |
| PlanetScale | Managed MySQL/Vitess DBaaS wrapper; no self-hostable engine. |
| Neon | Managed serverless Postgres DBaaS; no self-hostable engine. |
| MotherDuck | Managed DuckDB cloud service; no self-hostable engine. |
| TiDB Cloud / CockroachDB Cloud / Oracle Autonomous Database | Managed variants of engines already listed (TiDB, CockroachDB, Oracle Database). |
| Amazon DynamoDB | Managed-only; no self-hostable engine. |
| Google Cloud Bigtable | Managed-only; no self-hostable engine. |
| Amazon Neptune | Managed-only graph DBaaS; no self-hostable engine. |
| Pinecone | Managed-only vector DBaaS; no self-hostable engine. |
| FaunaDB (Fauna) | Service shut down; no self-hostable engine. |
| RethinkDB | Development discontinued; project shut down. |
| TigerGraph | Proprietary closed-source; no public engine repo to verify against. |
| Realm | Mobile embedded SDK rather than a standalone database engine; Device Sync deprecated. |
| PouchDB | Embedded in-browser JS library, not a standalone database engine. |
| LMDB | Embedded-only; canonical source is the OpenLDAP monorepo (GitHub is an unofficial mirror). |
| DBeaver / DataGrip / TablePlus / pgAdmin | Database GUI clients — clients, not engines. |
| Prisma / SQLAlchemy / Hibernate | ORMs — client libraries, not engines. |
| Flyway / Liquibase / Alembic | Migration tools, not engines. |

## Related

More curated lists by the same author:

- [Awesome-terminal](https://github.com/dakotac1994/Awesome-terminal) — terminal emulators and the terminal stack.
- [Awesome-diagram-tool](https://github.com/dakotac1994/Awesome-diagram-tool) — diagramming and visualization tools.
- [Awesome-chrome-extension](https://github.com/dakotac1994/Awesome-chrome-extension) — Chrome/Chromium browser extensions.
- [awesome-cli](https://github.com/dakotac1994/awesome-cli) — the broad CLI/TUI tools list.
- [awesome-oss-cli](https://github.com/dakotac1994/awesome-oss-cli) — the OSS-only CLI/TUI list.
- [awesome-oss-macos](https://github.com/Awesome-llms-labs/awesome-oss-macos) — open-source macOS apps.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). PRs welcome — every entry must be verified against an official source, with the license copied from the project's actual LICENSE file. In this space especially: never present a source-available or proprietary engine as open source.
