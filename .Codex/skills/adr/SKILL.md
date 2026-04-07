---
name: adr
description: Create a new Architecture Decision Record for: $ARGUMENTS
---

<!-- agent-notes: { ctx: "imported Claude command", deps: [.claude/commands/
adr
.md], state: active, last: "codex@2026-04-06" } -->

This skill is imported from [
adr
.md](/home/mahad/test/vteam-hybrid/.claude/commands/
adr
.md).
Use the source command as the canonical workflow; keep this wrapper thin.

## Imported Command

Create a new Architecture Decision Record for: $ARGUMENTS

Steps:
1. Determine the next ADR number by checking existing files in `docs/adrs/`.
2. Use the template at `docs/adrs/template.md`.
3. Fill in the context, decision, and consequences based on the topic provided.
4. Save as `docs/adrs/NNNN-<slug>.md` where NNNN is the zero-padded number and slug is a kebab-case title.
5. Add agent-notes frontmatter per `docs/methodology/agent-notes.md`.

