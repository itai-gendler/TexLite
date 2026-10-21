---
appliesTo:
- type: entity
  id: citation-tag
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

# Only the library's owner creates citation tags in it

Each person keeps their own set of citation tags.
