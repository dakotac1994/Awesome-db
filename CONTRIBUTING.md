# Contributing to Awesome-db

Thanks for helping keep this list accurate. This repo has strict honesty rules — please read them before opening a PR.

## What belongs here

- **Database engines / systems** organized by data model: relational, distributed SQL, document, key-value, wide-column, graph, time-series, vector, search, and OLAP/analytical.
- **Out of scope:** database GUI clients (DBeaver, DataGrip, TablePlus), ORMs (Prisma, SQLAlchemy), migration tools (Flyway, Liquibase), managed-DBaaS-only wrappers with no self-hostable engine (PlanetScale, Neon), BI dashboards, and data-integration/ETL tools. Deliberate exclusions live in the README's Notable exclusions table.

## Entry requirements (all must hold)

1. **Real and verifiable.** The engine must exist at the linked URL. `verified` is `true` only if you confirmed the entry on an official source (the project's repo, LICENSE file, or official site/docs) — never from a blog roundup alone.
2. **Honest license.** Copy the SPDX identifier from the project's actual LICENSE file — this list has several non-OSI licenses and getting them right is the whole point:
   - OSI-approved: `Apache-2.0`, `MIT`, `BSD-3-Clause`, `GPL-3.0-only`, `AGPL-3.0-only`, `PostgreSQL`, `MPL-2.0`…
   - Source-available / non-OSI: `BSL-1.1` (CockroachDB, Dragonfly…), `SSPL-1.0` (MongoDB…), `RSALv2`, `Elastic License 2.0`, `Timescale License`… — label exactly, never "open source".
   - `proprietary` for closed-source commercial engines (Oracle Database, Snowflake…).
   - If the license can't be confirmed, set `"license": null`, `"verified": false`, and explain in `"unverified_reason"`.
3. **No invented facts.** No guessed star counts, pricing, or descriptions. If you can't verify it, leave it `null` and say why.
4. **One category each.** Pick the single best-fitting `category` (the engine's primary data model).

## How to add an entry

1. Add the entry to `data/databases.json` (keep the file's existing ordering: grouped by category):
   ```json
   {
     "name": "ExampleDB",
     "description": "One-line description, no hype.",
     "license": "Apache-2.0",
     "category": "key-value",
     "repo": "https://github.com/org/exampledb",
     "homepage": "https://exampledb.org",
     "official_site": "https://exampledb.org",
     "stars": 1234,
     "verified": true,
     "unverified_reason": null
   }
   ```
   Use `null` (not `""`) for unknown `repo`/`official_site`/`stars`/`unverified_reason`.
2. Add the matching bullet to the right section in `README.md`: `- [ExampleDB](https://exampledb.org) — one-line description.`
3. Run the CI validation locally if you can (`python` 3.12+, see `.github/workflows/ci.yml`): it checks JSON validity, duplicate names/URLs, the README↔JSON cross-check, section counts, and TOC anchors.
4. Open a PR describing what you verified and where (link the official source — ideally the LICENSE file itself).

## Link hygiene

- Prefer `https://` URLs; no URL shorteners.
- If a project renamed/moved, update to the canonical URL and note it in `docs/status-changes.md`.
- License changes (relicensing events are common in this space) go in `docs/status-changes.md` too.

## What gets rejected

- Entries with invented licenses, stars, pricing, or descriptions.
- Source-available or proprietary engines presented as open source.
- Dead links, or projects you can't confirm exist.
- Clients, ORMs, migration tools, DBaaS wrappers — wrong list.
