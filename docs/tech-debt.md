---
agent-notes:
  ctx: "technical debt register for todo CLI"
  deps: [docs/scaffolds/tech-debt.md, docs/plans/2026-04-07-todo-cli-v1-plan.md]
  state: active
  last: "grace@2026-04-07"
  key: ["Grace tracks, Pat prioritizes against features"]
---
# Technical Debt Register

**Project:** Todo CLI
**Last reviewed:** 2026-04-07

## Active Debt

| ID | Description | Incurred | Why (business reason) | Est. cost to fix | Risk if left | Sprint to fix | Status |
|----|-------------|----------|----------------------|-----------------|-------------|--------------|--------|
| TD-001 | Natural language due-date parsing not in v1 (ISO only) | Sprint 1 | Ship faster with predictable parsing | S (0.5 day) | Medium: user friction on input | TBD | Open |
| TD-002 | No encryption-at-rest for local task file | Sprint 1 | Keep local setup simple | M (1-2 days) | Medium: privacy risk on shared machines | TBD | Open |

## Resolved Debt

| ID | Description | Incurred | Resolved | How it was fixed |
|----|-------------|----------|----------|-----------------|
| | | | | |

## Debt Categories

| Category | Count | Trend |
|----------|-------|-------|
| Missing tests | 0 | Stable |
| Hardcoded values | 0 | Stable |
| Missing error handling | 0 | Stable |
| Copy-paste duplication | 0 | Stable |
| Outdated dependencies | 0 | Stable |
| Missing docs | 0 | Stable |
| Performance | 0 | Stable |
| Security | 1 | Up |
| Accessibility | 0 | Stable |

## Review Cadence

- Sprint boundary: Grace reviews debt and Pat prioritizes paydown vs features.
- Every 3 sprints: full re-estimation and risk review.
