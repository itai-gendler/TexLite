---
appliesTo:
- type: entity
  id: login-session
  effect: removes
  contexts:
  - place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/auth.ts#registerAuthRoutes
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
permits:
- related:
  - verb: holds
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
---

# Account holders end their own sessions

Signing out ends the current session; changing one's password ends the person's other sessions.
