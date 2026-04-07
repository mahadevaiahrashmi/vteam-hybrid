---
agent-notes: { ctx: "ADR for Python CLI + local file persistence", deps: [docs/adrs/template.md, docs/tracking/2026-04-06-todo-cli-discovery.md], state: active, last: "archie@2026-04-07" }
---

# ADR-0003: Python CLI with Local File Persistence (JSON)

## Status

Accepted

## Context

The first release targets a single-user todo application with fast time-to-value. Confirmed requirements include CLI usage, CRUD operations, simple statuses (`todo`, `in-progress`, `done`), and both due date/time plus estimated duration per item. The user prioritized impact and speed, with a "start small and grow" scope style.

We need an implementation approach that minimizes setup while preserving data integrity and allowing iterative growth.

## Decision

Build the application as a Python CLI that stores data in a local JSON file.

- Language/runtime: Python 3.11+
- Interface: command-based CLI (non-interactive by default)
- Persistence: local JSON file on disk (single-user)
- Task schema includes: id, title, description (optional), status, due_at, estimate_minutes, created_at, updated_at
- Date/time format: ISO 8601 in UTC for persisted values

## Consequences

### Positive

- Very low setup friction: no DB server or service required.
- Fast implementation path aligned with v1 speed goals.
- Human-readable storage useful for debugging and manual recovery.

### Negative

- Limited concurrent-write safety compared to database-backed storage.
- Potential schema migration friction as complexity increases.
- Querying and sorting performance degrades if task volume grows significantly.

### Neutral

- Future migration path to SQLite remains straightforward because data model is small and explicit.
- JSON storage keeps initial architecture simple while preserving compatibility with a later storage adapter abstraction.

## Debate Notes (Wei Challenge Summary)

- Challenge: JSON may increase corruption risk on interrupted writes.
  Response: Use atomic write strategy (write temp file then rename) for persistence operations.
- Challenge: JSON can become hard to evolve at scale.
  Response: Keep a `schema_version` field and isolate storage behind repository functions for migration.
- Challenge: Filtering by due date may become inefficient.
  Response: v1 scale is single-user and small; reassess with usage telemetry before introducing SQLite.
