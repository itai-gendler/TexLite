---
appliesTo:
- type: entity
  id: account
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
- kind: code
  role: implementation
  target: src/client/App.tsx
---

# Team accounts are created by administrators

There is no public registration. A new account starts with the password the administrator sets; after an administrator resets a password, the person chooses a new one when they next sign in.
