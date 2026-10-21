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

# Discard Git changes

Return the files Git tracks to the current commit, dropping uncommitted changes to them.
