---
agent-notes: { ctx: "discovery tracking for todo CLI", deps: [docs/process/tracking-protocol.md, AGENTS.md], state: active, last: "cam@2026-04-06" }
---

# Discovery: Todo CLI

**Date:** 2026-04-06
**Lead:** Cam
**Status:** Complete
**Prior Phase:** None

## Key Decisions
- Chose a single-user product over team collaboration because the first release targets personal productivity only.
- Chose a CLI interface over web/mobile because the user explicitly prioritized command-line workflow for v1.
- Chose local file storage over a database because simplicity and low setup friction are primary goals for v1.
- Chose minimal status model (`todo`, `in-progress`, `done`) over richer workflows because simple status is sufficient for initial scope.
- Chose both due date/time and estimated duration over one time field because the user needs deadline and effort tracking.
- Chose Python as the implementation language because the user explicitly requested it.

## Artifacts Produced
- docs/tracking/2026-04-06-todo-cli-discovery.md

## Open Questions
- CLI UX style: subcommands only vs interactive prompts when arguments are missing.
- Date/time format and timezone behavior for due dates.
- Local storage format choice (JSON vs SQLite).

## Next Phase
- Phase 1b (Pat): capture product decision philosophy in docs/product-context.md.
