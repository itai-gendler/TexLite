---
appliesTo:
- type: entity
  id: account
  facts:
  - Password
references:
- kind: code
  role: implementation
  target: src/server/security.ts
---

# Passwords contain at least eight characters

Creation, reset, and change enforce the minimum password length.
