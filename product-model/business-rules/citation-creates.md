---
appliesTo:
- type: entity
  id: citation
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/citations.ts#registerCitationRoutes
permits:
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
---

# Only the library's owner saves citations into it

A person saves references into their own citation library only.
