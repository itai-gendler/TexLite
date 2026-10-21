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

# Reset password

Give a person a temporary password that they must change when they next sign in.
