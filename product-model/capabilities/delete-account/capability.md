---
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
- kind: code
  role: implementation
  target: src/client/pages/AdminUsers.tsx
domain: users
---

# Delete account

Remove a team account, choosing whether its owned projects transfer to the acting administrator or are deleted.
