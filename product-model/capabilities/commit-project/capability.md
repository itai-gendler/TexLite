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

# Commit project

Save current source changes as a Git commit with an explicit message.
