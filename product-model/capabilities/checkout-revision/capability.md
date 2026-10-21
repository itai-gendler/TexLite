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

# Checkout revision

Select a historical Git revision or return to the default branch, with an explicit force option.
