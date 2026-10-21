---
references:
- kind: code
  role: implementation
  target: src/server/routes/projectMembers.ts#registerProjectMemberRoutes
- kind: code
  role: implementation
  target: src/server/projects.ts#accessibleProject
---

# Membership

An existing account’s shared access to one project; the owner is represented by project ownership.

## Information kept

- **Role** — Read only or Read & write.
- **Member** — The participating account.
