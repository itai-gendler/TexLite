---
appliesTo:
- type: entity
  id: git-commit
  effect: reads
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

# Only the project owner sees Git history

Commits and their differences are shown only to the project owner.
