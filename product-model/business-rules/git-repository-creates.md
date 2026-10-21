---
appliesTo:
- type: entity
  id: git-repository
  effect: creates
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

# Only the project owner creates its GitHub repository

Creating the GitHub destination also starts the project's local Git repository.
