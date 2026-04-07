---
agent-notes: { ctx: "plan tracking for todo CLI", deps: [docs/plans/2026-04-07-todo-cli-v1-plan.md, docs/test-strategy.md, docs/tech-debt.md], state: active, last: "grace@2026-04-07" }
---

# Plan: Todo CLI

**Date:** 2026-04-07
**Lead:** Grace
**Status:** Complete
**Prior Phase:** docs/tracking/2026-04-07-todo-cli-architecture.md

## Key Decisions
- Chose command-first delivery sequence (model -> storage -> commands) to ship usable increments quickly.
- Chose pytest-based unit + integration testing over broader test stack to keep v1 lightweight.
- Chose to defer natural-language date parsing to post-v1 as explicit managed debt.
- Chose to track local-file privacy hardening as early debt instead of blocking v1 delivery.

## Artifacts Produced
- docs/plans/2026-04-07-todo-cli-v1-plan.md
- docs/test-strategy.md
- docs/tech-debt.md

## Open Questions
- Exact CLI UX polish level for first cut (table output vs plain list).
- Preferred default command for listing (all vs active-first).

## Next Phase
- Board setup, sprint item creation, and implementation start.
