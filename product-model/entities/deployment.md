---
singleton: true
references:
- kind: code
  role: implementation
  target: src/server/config.ts
- kind: code
  role: implementation
  target: src/server/routes/system.ts
---

# Deployment

The single instance’s effective writing limits and available compiler options.

## Information kept

- **Project latexmkrc allowed** — Whether owners can select an existing project latexmkrc.
- **Allowed engines** — The host engines exposed to projects.
- **Compile timeout** — The time limit per compile.
- **Compile capacity** — The global concurrent compile limit.
- **Upload limit** — The maximum upload size.
- **History limits** — The optional cap on ordinary snapshots and their soft storage limit.
- **Selection history limit** — The independent edit-trail storage budget.
