---
appliesTo:
- type: entity
  id: account
- type: entity
  id: administrator
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
---

# An administrator cannot remove or demote themselves, nor the last administrator

The acting administrator cannot delete their own account or change it to User, and the last active administrator cannot be deleted or demoted.
