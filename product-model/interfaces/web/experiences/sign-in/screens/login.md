---
entities:
- entity: account
  collects:
  - Username
  - Password
references:
- kind: code
  role: implementation
  target: src/client/pages/AuthPages.tsx
---

# Login

Supply credentials for an existing team account.
