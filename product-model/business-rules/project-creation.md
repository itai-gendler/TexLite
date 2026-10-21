---
appliesTo:
- type: entity
  id: project
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/projects.ts#registerProjectCatalogRoutes
permits:
- actors:
  - administrator
- actors:
  - user
  when:
  - entity: account
    fact: Project creation allowed
    is: true
---

# Only administrators and users allowed to create projects create, import or duplicate projects

Administrators can always create projects; a user can when an administrator has allowed it. Everyone can still work in projects shared with them.
