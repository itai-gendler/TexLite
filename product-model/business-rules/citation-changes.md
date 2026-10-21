---
appliesTo:
- type: entity
  id: citation
  effect: changes
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

# Only its owner changes a citation

The citation library is private: a saved reference is edited, refreshed and tagged only by the account that saved it.
