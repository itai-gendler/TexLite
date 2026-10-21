---
appliesTo:
- type: entity
  id: citation
  effect: reads
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

# Only its owner sees a citation

No one else, administrators included, sees another person's citation library.
