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

# Push project

Push the current Git repository branch to its configured GitHub destination using the current owner’s connection.
