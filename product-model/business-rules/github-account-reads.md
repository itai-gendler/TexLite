---
appliesTo:
- type: entity
  id: github-account
  effect: reads
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

# Only the account holder sees their GitHub connection

Other people, project members included, never see someone's GitHub login or token.
