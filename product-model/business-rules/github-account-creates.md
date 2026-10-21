---
appliesTo:
- type: entity
  id: github-account
  effect: creates
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

# Only the account holder connects their GitHub account

The token is verified with GitHub before it is saved.
