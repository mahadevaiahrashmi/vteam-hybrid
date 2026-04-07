---
agent-notes:
  ctx: "test strategy for Python todo CLI"
  deps: [docs/scaffolds/test-strategy.md, docs/plans/2026-04-07-todo-cli-v1-plan.md]
  state: active
  last: "tara@2026-04-07"
  key: ["Tara owns, created during kickoff"]
---
# Test Strategy

**Project:** Todo CLI
**Last reviewed:** 2026-04-07

## Testing Principles

1. Test behavior, not implementation.
2. Keep tests fast and deterministic.
3. Every bug gets a regression test before fix.
4. Favor table-driven tests for command and validation paths.

## Test Pyramid

### Unit Tests
- **Scope:** date/status validation, model transforms, storage helpers.
- **Coverage target:** 90%+ line coverage on business logic modules.
- **Framework:** `pytest`
- **Run command:** `pytest -q`
- **Speed target:** full unit suite under 20 seconds.

### Integration Tests
- **Scope:** CLI command behavior against temporary local data files.
- **Coverage target:** all core commands and unhappy paths.
- **Framework:** `pytest` with subprocess/CLI fixtures.
- **Run command:** `pytest -q tests/integration`
- **Dependencies:** temporary filesystem sandbox.

### End-to-End Tests
- **Scope:** Not required for v1 (single local CLI with no network/UI stack).
- **Coverage target:** deferred.
- **Framework:** N/A
- **Run command:** N/A
- **Flaky test policy:** N/A

## What Gets Tested Where

| Area | Unit | Integration | E2E | Notes |
|------|------|-------------|-----|-------|
| Task model validation | Yes | — | — | Status and datetime constraints |
| File persistence | Yes | Yes | — | Atomic write and read recovery |
| CLI command parsing | — | Yes | — | Argument and option handling |
| CRUD workflows | — | Yes | — | Create/list/show/update/delete |
| Error handling | Yes | Yes | — | Invalid status/date/ID paths |

## What Is NOT Tested (and why)

| Area | Reason |
|------|--------|
| Cross-platform shell behavior edge cases | Deferred until packaging/distribution phase |
| Multi-user concurrency | Out of scope for single-user v1 |

## Coverage Gates

| Scope | Metric | Threshold | Enforced by |
|-------|--------|-----------|-------------|
| Overall | Line coverage | 85% | CI / local gate |
| New code | Line coverage | 90% | Code review (Tara) |
| Critical paths | Branch coverage | 90% | Code review (Tara) |

## Test Data Strategy

- Use temp directories/files per test for isolation.
- Use table-driven fixtures for status/date permutations.
- Never use real personal task data in tests.
- Snapshot tests limited to stable help/list output formatting.
