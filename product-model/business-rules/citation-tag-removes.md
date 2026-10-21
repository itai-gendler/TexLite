---
appliesTo:
- type: entity
  id: citation-tag
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

# Only its owner deletes a citation tag

Deleting a citation tag removes it from the owner's citations and keeps the citations.
