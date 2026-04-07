---
name: scaffold-docs
description: Use the project's scaffold documentation templates when initializing or extending repo docs.
---

<!-- agent-notes: { ctx: "scaffold docs import", deps: [docs/scaffolds], state: active, last: "codex@2026-04-06" } -->

Use this skill when work should start from the project's scaffold templates rather than inventing new documentation structure.

The canonical scaffold source is [docs/scaffolds](/home/mahad/test/vteam-hybrid/docs/scaffolds). A project-local mirror also exists at [.Codex/scaffolds](/home/mahad/test/vteam-hybrid/.Codex/scaffolds) for Codex-oriented discovery.

## Available Scaffold Templates

- [code-map.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/code-map.md)
- [config-manifest.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/config-manifest.md)
- [dependency-decisions.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/dependency-decisions.md)
- [performance-budget.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/performance-budget.md)
- [README.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/README.md)
- [runbook-template.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/runbook-template.md)
- [sbom.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/sbom.md)
- [tech-debt.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/tech-debt.md)
- [test-strategy.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/test-strategy.md)
- [threat-model.md](/home/mahad/test/vteam-hybrid/docs/scaffolds/threat-model.md)

## Guidance

- Prefer copying or adapting a scaffold template over drafting a new document from scratch.
- Treat the files under [docs/scaffolds](/home/mahad/test/vteam-hybrid/docs/scaffolds) as the source of truth if the mirror ever drifts.
- When initialization commands such as `quickstart`, `kickoff`, or a scaffold command mention moving templates into final locations, use these scaffold docs.
