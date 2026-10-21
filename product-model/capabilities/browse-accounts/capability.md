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

# Browse accounts

Show matching accounts with creation permission and owned-project counts, with twenty results per page.
