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

# Create account

Create an account with the supplied username, display name, password, and creation permission.
