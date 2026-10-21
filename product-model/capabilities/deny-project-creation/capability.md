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

# Deny project creation

Stop a User from creating, importing and duplicating projects.
