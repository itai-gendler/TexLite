---
appliesTo:
- type: entity
  id: login-session
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/auth.ts#registerAuthRoutes
permits:
- actors:
  - visitor
---

# A visitor starts a session only with valid credentials

The username and password must identify an enabled account.
