---
appliesTo:
- type: entity
  id: user
  effect: removes
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
permits:
- actors:
  - administrator
---

# Only administrators take away the User role

The User role is replaced when an administrator makes the account an administrator.
