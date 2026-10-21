---
appliesTo:
- type: entity
  id: login-session
  effect: removes
  contexts:
  - place: web::administration::users
permits:
- actors:
  - administrator
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
---

# Only administrators sign other people out, by resetting a password or deleting an account

Resetting a person's password or deleting their account signs that person out everywhere.
