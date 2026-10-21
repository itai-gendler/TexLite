---
appliesTo:
- type: entity
  id: account
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

# Only administrators delete team accounts

An administrator deletes another person's account from Users; the person's own sessions end with it.
