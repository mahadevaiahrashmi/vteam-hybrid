---
agent-notes: { ctx: "product decision philosophy for todo CLI", deps: [docs/tracking/2026-04-06-todo-cli-discovery.md], state: active, last: "pat@2026-04-07" }
---
# Product Context

**Last updated:** 2026-04-07
**Updated by:** Pat (Phase 1b)

## Decision Philosophy
- Prioritize user impact when features compete for the same sprint.
- Prefer fast delivery over polish for early iterations when value can ship safely.
- Favor reversible decisions and short feedback loops.

## Quality Bar
- Core commands must be reliable for everyday use: create, list, update, delete, and status change.
- No silent data loss in normal CLI workflows.
- Error messages must tell the user how to correct invalid input.

## Scope Style
- Start small and grow incrementally.
- Ship a useful MVP quickly, then improve based on real usage.
- Avoid complex dependencies in v1 unless they reduce meaningful risk.

## User Model
- Primary user is a single person managing personal tasks from a terminal.
- User cares about speed, low friction, and clear visibility into due dates and completion state.
- Biggest frustration to solve: forgetting deadlines and losing clarity on what to do next.

## Non-Negotiables
- Reject if task data can be lost or corrupted through normal CLI usage.
- Reject if due date/time cannot be set and viewed consistently.
- Reject if status transitions are confusing or inconsistent.

## Correction Log
| Date | What Changed | Reason |
|------|-------------|--------|
| 2026-04-07 | Initial product context created | Kickoff Phase 1b elicitation and assumptions |
