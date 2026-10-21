---
appliesTo:
- type: entity
  id: user
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
permits:
- actors:
  - administrator
---

# Only administrators give an account the User role

New accounts are Users unless the administrator chooses Administrator.
