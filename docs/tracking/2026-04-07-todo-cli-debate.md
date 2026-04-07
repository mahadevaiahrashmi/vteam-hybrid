---
agent-notes: { ctx: "debate tracking for todo CLI ADR", deps: [docs/adrs/0003-python-cli-local-file-store.md, docs/process/team-governance.md], state: active, last: "wei@2026-04-07" }
---

# Debate: Todo CLI Storage and Runtime

**ADR:** docs/adrs/0003-python-cli-local-file-store.md
**Date:** 2026-04-07
**Participants:** Archie (author) vs Wei (challenger)

## Round 1 — Wei's Challenges

1. JSON persistence risks partial-write corruption if the process exits mid-write.
2. JSON may become a trap if scope grows to recurring tasks, tags, or search.
3. UTC persistence can confuse users who expect local-time display semantics in CLI output.

## Round 2 — Archie's Responses

1. Use atomic writes (`tmp` + rename) and fail-safe rollback to last known-good file.
2. Isolate persistence behind a storage module and include `schema_version` now so migration to SQLite is low-risk.
3. Persist UTC for consistency but render in local time by default in list/detail output.

## Round 3 — Final Word (if needed)

No further rebuttal required for kickoff-level architecture.

## Resolution

- **Resolved:** Corruption mitigation, migration strategy, timezone handling approach.
- **Accepted risks:** JSON query scalability beyond small single-user datasets.
- **ADR changes:** Added atomic write, schema version, and UTC persistence with local-time display guidance.
