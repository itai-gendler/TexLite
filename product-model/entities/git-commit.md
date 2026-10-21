---
domain: git
references:
- kind: code
  role: implementation
  target: src/server/git.ts#ProjectGitService
- kind: code
  role: implementation
  target: src/client/GitDialog.tsx
---

# Git commit

An independently inspectable and selectable Git revision.

## Information kept

- **Revision** — The commit identity.
- **Message** — The owner-entered commit message.
- **Author** — The commit author.
- **Time** — When the commit was made.
- **Difference** — The source changes belonging to this revision.
