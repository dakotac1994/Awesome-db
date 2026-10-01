# Glossary

Terms you'll meet across the [Awesome-db](../README.md) catalog.

- **ACID** — Atomicity, Consistency, Isolation, Durability: the transaction guarantees of traditional relational databases. If your workload needs "the money moved exactly once," you want ACID.
- **BASE** — Basically Available, Soft state, Eventually consistent: the relaxed counterpart to ACID, common in distributed NoSQL systems that prioritize availability.
- **CAP theorem** — a distributed system can guarantee only two of Consistency, Availability, and Partition tolerance. In practice: choose CP or AP behavior when the network splits.
- **OLTP** — online transaction processing: many small, fast reads/writes (checkout flows, user records). Row stores and relational engines dominate here.
- **OLAP** — online analytical processing: few large scans/aggregations over big datasets (dashboards, reporting). Columnar engines dominate here.
- **Row store vs columnar store** — row stores keep whole records together (fast point lookups); columnar stores keep each column together (fast scans/aggregations, heavy compression).
- **Sharding** — splitting data across nodes by key range or hash so the dataset exceeds one machine. The core scaling primitive of distributed databases.
- **Replication** — keeping copies of data on multiple nodes for availability and read scaling; primary/replica (async) vs multi-primary vs consensus-based (Raft/Paxos).
- **Consensus (Raft/Paxos)** — protocols that let a cluster agree on a single value/log order despite failures; the backbone of CP distributed SQL systems.
- **LSM-tree** — log-structured merge-tree: write-optimized storage (memtable + SSTables, background compaction). Used by RocksDB, Cassandra, ScyllaDB, LevelDB.
- **B-tree / B+tree** — the classic read-optimized index structure; used by PostgreSQL, MySQL/InnoDB, SQLite.
- **WAL (write-ahead log)** — durability primitive: changes are appended to a log before being applied, so crashes can replay.
- **MVCC** — multi-version concurrency control: readers see snapshots without blocking writers; how Postgres/MySQL give you isolation without heavy locking.
- **NewSQL / Distributed SQL** — relational engines built for horizontal scale and strong consistency (CockroachDB, YugabyteDB, TiDB, Spanner): SQL + sharding + consensus.
- **Document database** — stores JSON-like documents with flexible schemas; query by fields, secondary indexes (MongoDB, CouchDB, FerretDB).
- **Key-value store** — the simplest model: opaque values addressed by key; the speed layer (Redis, Valkey, etcd, RocksDB).
- **Wide-column store** — sparse two-dimensional keyspace: row key → column families → columns; built for massive scale (Cassandra, ScyllaDB, HBase).
- **Graph database** — nodes, edges, and properties as first-class citizens; traversals instead of joins (Neo4j, Kuzu, Memgraph). Property graph vs RDF triple-store are the two flavors.
- **Time-series database** — optimized for timestamped measurements: high-ingest, retention policies, downsampling (InfluxDB, TimescaleDB, QuestDB).
- **Vector database** — stores embeddings and answers nearest-neighbor queries (ANN indexes like HNSW, IVF) for semantic/AI search (Qdrant, Milvus, Weaviate, pgvector).
- **Embeddings** — dense numeric vectors representing text/images; the bridge between LLMs and vector databases.
- **ANN (approximate nearest neighbor)** — index families (HNSW, IVF-PQ, DiskANN) that trade a little recall for orders-of-magnitude faster vector search.
- **Full-text search** — inverted indexes over tokenized text with relevance ranking (BM25); the Elasticsearch/OpenSearch/Meilisearch/Typesense domain.
- **Inverted index** — term → list of documents containing it; the core data structure of search engines.
- **HTAP** — hybrid transactional/analytical processing: one engine claiming to do both OLTP and OLAP well (TiDB, SingleStore).
- **Embedded database** — runs in-process inside your application, no server (SQLite, DuckDB, RocksDB, PouchDB).
- **SSPL (Server Side Public License)** — MongoDB's non-OSI copyleft license: offering the software as a service triggers source-release obligations. Not OSI-approved — labeled, never "open source".
- **BSL (Business Source License)** — source-available, converts to an OSI license after a delay (CockroachDB, Dragonfly, Couchbase use variants). Not OSI-approved at publication time.
- **RSALv2 / SSPLv1** — the licenses Redis used during 2024–2025 before returning to AGPLv3 with Redis 8; the canonical relicensing saga — see [status-changes](status-changes.md).
- **Source-available** — you can read the code, but the license restricts use (often: competing SaaS offerings). Distinct from open source; this list labels it exactly.
- **DBaaS** — database-as-a-service: someone else runs the engine (Neon, PlanetScale, Pinecone Cloud). Out of scope for this list unless the engine itself is the entry.
- **ORM** — object-relational mapper (Prisma, SQLAlchemy, Hibernate): a client-side library, not a database — out of scope.
- **Migration tool** — schema-versioning tooling (Flyway, Liquibase, Alembic): out of scope.
- **Polyglot persistence** — using multiple database models for different workloads in one system; the reason this list has ten sections.
