---
appliesTo:
- type: entity
  id: citation
  effect: removes
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

# Only its owner deletes a citation

A saved reference is deleted only by the account that saved it.
