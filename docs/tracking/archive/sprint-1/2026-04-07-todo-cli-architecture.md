---
agent-notes: { ctx: "architecture tracking for todo CLI", deps: [docs/adrs/0003-python-cli-local-file-store.md, docs/security/threat-model.md, docs/tracking/2026-04-07-todo-cli-debate.md], state: active, last: "archie@2026-04-07" }
---

# Architecture: Todo CLI

**Date:** 2026-04-07
**Lead:** Archie
**Status:** Complete
**Prior Phase:** docs/tracking/2026-04-06-todo-cli-discovery.md

## Key Decisions
- Chose Python CLI over web/mobile architecture because user confirmed CLI-only v1.
- Chose local JSON file persistence over database service because startup friction and delivery speed are primary.
- Chose UTC persistence with local-time rendering to balance storage consistency and user readability.
- Chose atomic write strategy to reduce corruption risk in local-file storage.

## Artifacts Produced
- docs/adrs/0003-python-cli-local-file-store.md
- docs/security/threat-model.md
- docs/tracking/2026-04-07-todo-cli-debate.md

## Open Questions
- Final default storage path convention by OS.
- Whether v1 should include file backup rotation or only atomic writes.

## Next Phase
- Phase 4 acceptance criteria and Phase 5 implementation planning.
