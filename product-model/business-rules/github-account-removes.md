---
appliesTo:
- type: entity
  id: github-account
  effect: removes
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

# Only the account holder disconnects their GitHub account

Removing the token stops pushes for the projects that person owns.
