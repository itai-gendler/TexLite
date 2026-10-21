---
domain: git
relations:
- entity: git-commit
  verb: contains
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/server/git.ts#ProjectGitService
- kind: code
  role: implementation
  target: src/client/GitDialog.tsx
---

# Git repository

A project’s local Git work and optional GitHub destination.

## Information kept

- **Remote** — The GitHub repository address.
- **Name** — The repository name.
- **Visibility** — Private or public when created.
- **Branch** — The current branch or detached revision.
- **Default branch** — The branch to return to from an inspected revision.
- **Changes** — Current staged, unstaged, and untracked source differences.
- **Pushed** — The latest push result.
