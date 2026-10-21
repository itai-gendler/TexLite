---
appliesTo:
- type: entity
  id: administrator
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
permits:
- actors:
  - administrator
---

# Only administrators make an account an administrator

An administrator gives the Administrator role when adding an account or by changing an existing account's role.
