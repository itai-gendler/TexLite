---
appliesTo:
- type: entity
  id: git-commit
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/projectGit.ts#registerProjectGitRoutes
permits:
- related:
  - verb: contains
    entity: git-repository
  - verb: keeps
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: contains
    entity: git-repository
  - verb: keeps
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
---

# Only the project owner commits

Git backup is owner-only; members, Read & write included, do not commit.
