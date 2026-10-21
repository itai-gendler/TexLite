---
appliesTo:
- type: entity
  id: collaboration-session
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

# Only administrators end other people's sessions, by resetting a password or deleting an account

Resetting a person's password or deleting their account ends that person's open sessions.
