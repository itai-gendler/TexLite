---
appliesTo:
- type: entity
  id: account
  effect: changes
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

# Only administrators change team accounts

Role, project-creation permission and password resets are changed by an administrator from Users; other people cannot change someone else's account.
