---
appliesTo:
- type: entity
  id: project
  effect: removes
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

# Only administrators delete a removed account's projects

When an administrator deletes an account and chooses to delete its projects, the owned projects go with it, together with their files, output and history.
