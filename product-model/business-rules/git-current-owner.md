---
appliesTo:
- type: entity
  id: git-repository
- type: entity
  id: github-account
references:
- kind: code
  role: implementation
  target: src/server/git.ts#ProjectGitService
- kind: code
  role: implementation
  target: src/server/routes/projectMembers.ts#registerProjectMemberRoutes
---

# GitHub backup uses the project’s current owner connection

A saved remote stays with the project through transfer; personal credentials remain with their own accounts. Push requires a configured destination, a commit and an attached branch.
