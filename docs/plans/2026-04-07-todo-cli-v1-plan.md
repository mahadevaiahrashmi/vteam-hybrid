---
agent-notes: { ctx: "implementation plan for todo CLI v1", deps: [docs/tracking/2026-04-06-todo-cli-discovery.md, docs/adrs/0003-python-cli-local-file-store.md, docs/product-context.md], state: active, last: "grace@2026-04-07" }
---
# Plan: Todo CLI v1

## Goal

Deliver a single-user Python CLI todo app that supports CRUD, status updates, and both due date/time plus estimated duration using local file persistence.

## Constraints

- Python implementation required.
- Single-user, local-first, no accounts for v1.
- Required statuses: `todo`, `in-progress`, `done`.
- Required time fields per item: due date/time and estimated duration.
- Architecture decision fixed by ADR-0003.

## Architecture Gate Items

- Item: Persistence strategy and schema design.
  - Gate status: Complete (ADR-0003 + Wei challenge + debate tracked).

## Approach

1. Define task model and validation utilities.
2. Implement storage module with atomic JSON read/write and schema versioning.
3. Implement CLI commands:
   - `add`
   - `list`
   - `show`
   - `update`
   - `delete`
   - `status`
4. Add sorting/filter behavior for list output (status + due date views).
5. Add robust error handling and clear user-facing messages.
6. Add tests (unit + integration-style CLI command tests).
7. Update docs (usage examples and local data-file behavior).

## Personas Involved

- Tara: tests-first for all command behaviors and edge cases.
- Sato: implementation and refactor.
- Vik: maintainability review.
- Pierrot: local-file and input-handling security review.
- Grace: tracking and board status enforcement.

## Open Questions

- Preferred default timezone display in CLI output (assumed: local timezone display, UTC persistence).
- Whether to support natural language date parsing in v1 (assumed: no, strict ISO input).

## Acceptance Criteria

- User can create a todo item with title, due date/time, and estimated duration.
- User can list all items with ID, title, status, due date/time, and estimate.
- User can view a single item by ID.
- User can update title, due date/time, estimate, and description.
- User can update status among `todo`, `in-progress`, `done`.
- User can delete an item by ID.
- Invalid dates, statuses, and IDs return clear non-zero-error responses.
- Data persists across CLI runs in a local file without silent corruption.
