---
appliesTo:
- type: entity
  id: github-account
  effect: changes
references:
- kind: code
  role: implementation
  target: src/server/routes/projectGit.ts#registerProjectGitRoutes
permits:
- related:
  - verb: connects
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: connects
    entity: account
  - verb: uses
    entity: administrator
---

# Only the account holder replaces their GitHub token

A GitHub connection belongs to a TexLite account, not to a project.
