---
references:
- kind: code
  role: implementation
  target: src/client/GitDialog.tsx
---

# Git

Optional Git backup of a project to GitHub, used by the project owner: the local repository, commits, pushes and checkouts.

## Boundary

Owns revision backup and checkout; it does not own automatic snapshots.
