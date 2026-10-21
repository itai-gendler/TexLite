---
entities:
- entity: account
  shows:
  - Username
  - Display name
  - Project creation allowed
  collects:
  - Username
  - Display name
  - Password
  - Project creation allowed
- user
- administrator
references:
- kind: code
  role: implementation
  target: src/client/pages/AdminUsers.tsx
---

# Users

The administrators' list of team accounts, where people are added, their role and project-creation permission changed, passwords reset and accounts deleted.
