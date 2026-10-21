---
appliesTo:
- type: entity
  id: account
  effect: changes
  contexts:
  - place: web::writing::password
references:
- kind: code
  role: implementation
  target: src/server/routes/auth.ts#registerAuthRoutes
permits:
- related:
  - verb: uses
    entity: user
- related:
  - verb: uses
    entity: administrator
---

# Account holders change only their own password

Changing a password requires the current one.
