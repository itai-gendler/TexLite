---
appliesTo:
- type: entity
  id: account
  effect: creates
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

# Only administrators create team accounts

Every account is added by an administrator from Users; nobody signs themselves up.
