---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/projectGit.ts#registerProjectGitRoutes
- kind: code
  role: implementation
  target: src/server/git.ts#ProjectGitService
- kind: code
  role: implementation
  target: src/client/GitDialog.tsx
domain: git
---

# Browse Git

Inspect local working changes, commit history, revision differences, and the GitHub destination. Git must be available on the host.
