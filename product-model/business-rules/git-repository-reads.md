---
appliesTo:
- type: entity
  id: git-repository
  effect: reads
references:
- kind: code
  role: implementation
  target: src/server/routes/projectGit.ts#registerProjectGitRoutes
permits:
- related:
  - verb: keeps
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: keeps
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
---

# Only the project owner sees the project's Git status

Members, Read & write included, do not see it.
