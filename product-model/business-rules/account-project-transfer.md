---
appliesTo:
- type: entity
  id: project
  effect: changes
  facts:
  - Owner
  contexts:
  - place: web::administration::users
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
permits:
- actors:
  - administrator
---

# Only administrators take over a removed account's projects

When an administrator deletes an account and keeps its projects, ownership of every project it owned passes to that administrator.
