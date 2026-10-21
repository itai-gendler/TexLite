---
appliesTo:
- type: entity
  id: account
  effect: reads
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

# Only administrators browse team accounts

Users lists every account with its role, project-creation permission and number of owned projects, and only administrators reach it.
