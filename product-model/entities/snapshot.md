---
domain: history
references:
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
- kind: code
  role: implementation
  target: src/server/routes/projectHistory.ts#registerProjectHistoryRoutes
---

# Snapshot

A recoverable copy of the project's files and effective compiler settings, taken automatically when files change.

## Information kept

- **Created** — The snapshot time.
- **Author** — A single contributor when attributable, otherwise no single author.
- **Reason** — Project created, automatic save, file operation, Git operation, safety checkpoint, or restored version.
- **Label** — An optional name a person gives it, which also protects it from pruning.
- **Changed paths** — Files added, changed, or deleted.
- **Files** — The recoverable source and attachment contents.
- **Compiler settings** — Main document, engine, selected latexmkrc, and ChkTeX choice.
- **Fingerprint** — Identifies the exact contents a person inspected, so a restore applies only those.
- **Storage** — Logical file, metadata, and protected storage usage.
