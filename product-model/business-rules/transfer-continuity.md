---
appliesTo:
- type: entity
  id: project
- type: entity
  id: membership
- type: entity
  id: github-account
references:
- kind: code
  role: implementation
  target: src/server/routes/projectMembers.ts#registerProjectMemberRoutes
- kind: code
  role: implementation
  target: src/server/git.ts#ProjectGitService
---

# A transferred project keeps the previous owner as an editor

Transfer promotes the selected active account to owner, absorbs its old membership if present, and grants the previous owner Read & write. The new owner’s GitHub connection is used for later remote operations.
