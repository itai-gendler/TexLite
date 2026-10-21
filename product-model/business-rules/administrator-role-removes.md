---
appliesTo:
- type: entity
  id: administrator
  effect: removes
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
permits:
- actors:
  - administrator
---

# Only administrators take away the Administrator role

An administrator changes another administrator's role to User; the protections for the acting and the last administrator still apply.
