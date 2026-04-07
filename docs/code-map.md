---
agent-notes:
  ctx: "codebase structural overview for todo CLI"
  deps: [docs/scaffolds/code-map.md]
  state: active
  last: "coordinator@2026-04-07"
  key: ["update when commands, modules, or APIs change"]
---
# Code Map

Structural overview of the todo CLI codebase.

## Architecture at a Glance

```text
CLI Input -> Command Parser -> Task Service -> JSON Storage
     ^                                          |
     |-------------- formatted output ----------|
```

## Dependency Graph

```text
cli (entrypoint)
  -> commands (add/list/show/update/delete/status)
  -> services (task operations + validation)
  -> storage (json read/write, atomic persistence)
  -> models (task schema, enums)
```

## Package / Module Summaries

### app (planned) — Python CLI Todo App

**Purpose:** Single-user task management from terminal.

| Module | Key Exports | Notes |
|--------|-------------|-------|
| `src/todo_cli/main.py` | `main()` | CLI entrypoint |
| `src/todo_cli/commands.py` | command handlers | Subcommand dispatch |
| `src/todo_cli/models.py` | `Task`, `TaskStatus` | Domain model |
| `src/todo_cli/storage.py` | `load_tasks()`, `save_tasks()` | Local JSON persistence |
| `src/todo_cli/service.py` | CRUD/status APIs | Business logic |

**External deps:** Python stdlib (initially)
**Internal deps:** N/A

## Test Inventory

| Package | Test Files | Tests | Focus |
|---------|------------|-------|-------|
| `tests/unit` | Planned | Planned | Validation and storage helpers |
| `tests/integration` | Planned | Planned | CLI behavior and workflows |

## Key Type Flow

CLI args -> validated command DTO -> Task model -> persisted JSON document -> formatted CLI output

## Config Structure

- Local storage path via CLI option or default location.
- Time persisted in UTC ISO 8601; rendered in local timezone by default.
