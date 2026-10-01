# Status changes

Renames, license changes, archival notices, and shutdowns affecting the [Awesome-db](../README.md) catalog. Newest first.

## 2026-09-30

Kuzu removed from catalog (archived): the kuzudb/kuzu repo was archived 2025-10-10 after the sponsoring company shut down, and kuzudb.com is offline. Moved to Notable exclusions. Catalog now 72 entries, 72/72 verified.

Rebrands verified and URLs updated:
- ArangoDB → arango.ai (official site rebranded from arangodb.com).
- TimescaleDB → tigerdata.com (Timescale rebranded to Tiger Data; product still TimescaleDB).

FerretDB's website (ferretdb.com) returned 404 to automated checks on 2026-09-30 while the project itself is active (repo pushed 2026-06-05); entry now links to the official docs at docs.ferretdb.io.

Lychee exclusions added after CI failures on 2026-09-30: cockroachdb.com (connection resets), mysql.com (403), milvus.io (302 redirect loop) — all bot-detection false positives on live official sites, excluded with domain-bare patterns per AGENTS.md lesson.

Catalog created: 73 entries, 73/73 verified against official sources (repo LICENSE files, official sites/docs). License states below are what each project's LICENSE file said on this date — this space relicenses often, so treat this log as the paper trail.

### Notable license verdicts at creation

| Engine | Labeled license | Notes |
| --- | --- | --- |
| Redis | AGPL-3.0-only | Redis 8 LICENSE is a **choice of three**: AGPLv3 / SSPLv1 / RSALv2. We label the OSI-approved option; the 2024 relicensing (RSALv2+SSPLv1) ended with AGPLv3's return in 2025. |
| Valkey | BSD-3-Clause | Linux Foundation fork of Redis. |
| CockroachDB | proprietary | **No longer BSL.** Commit c0274df moved all releases after Nov 18, 2024 to the custom CockroachDB Software License (license key required for production). |
| MongoDB | SSPL-1.0 | Not OSI-approved; labeled as such. |
| Elasticsearch | AGPL-3.0-only / SSPL-1.0 / Elastic License 2.0 | Triple license is now the repo default (AGPLv3 option added 2024); x-pack files remain solely Elastic License 2.0. |
| ScyllaDB | ScyllaDB-Source-Available | Moved off AGPL in Dec 2024; 6.2 was the final AGPL release. Not an SPDX ID — labeled exactly. |
| ArangoDB | BSL-1.1 | Switched from Apache-2.0; converts to Apache-2.0 on the 4-year Change Date. |
| Memgraph | BSL-1.1 | BSL-1.1 / Memgraph Enterprise License per file. |
| Dragonfly | BSL-1.1 | Converts to Apache-2.0 on Nov 1, 2030. |
| Couchbase Server | BSL-1.1 | Since Server 7 (2021). |
| TimescaleDB | Apache-2.0 + Timescale License | Repo LICENSE: "variously licensed" across the two. |
| Weaviate | BSD-3-Clause + Weaviate License | Repo LICENSE: "variously licensed" across the two. |
| InfluxDB 3.x | MIT / Apache-2.0 | Dual MIT OR Apache-2.0. |
| Meilisearch | MIT + BSL-1.1 | Mixed across components; labeled as found. |
| RavenDB | AGPL-3.0-only | Community server; a commercial license key swaps it to a EULA. |
| RocksDB | Apache-2.0 AND GPL-2.0 | Dual license (LICENSE.Apache + LICENSE.leveldb). |
| H2 | MPL-2.0 OR EPL-1.0 | Dual license. |
| Firebird | IDPL-1.0 | Confirmed via firebirdsql.org's official license page. |
| SQLite | public domain | Per sqlite.org/copyright.html. |
| MySQL (Community) | GPL-2.0-only | GPLv2. |
| Citus | AGPL-3.0-only | Distributed Postgres extension. |
| YugabyteDB | Apache-2.0 | Core components (DocDB, YSQL, Java clients) under Apache-2.0. |
| StarRocks | Apache-2.0 | Confirmed in LICENSE.txt at repo root. |
| libSQL | MIT | Turso's SQLite fork. |
| Dgraph | Apache-2.0 | No change. |
| Neo4j | GPL-3.0-only | Community edition; Enterprise is commercial. |
| Typesense | GPL-3.0-only | No change. |

### Notable deaths and exclusions (not entries)

- **FaunaDB (Fauna)** — service shut down; excluded.
- **RethinkDB** — development discontinued; excluded.
- **Realm** — mobile embedded SDK, not a standalone engine; MongoDB deprecated Realm Device Sync.
- **PouchDB** — in-browser JS library, not a standalone engine.
