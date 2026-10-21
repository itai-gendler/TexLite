---
appliesTo:
- type: entity
  id: citation-tag
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

# Only its owner sees a citation tag

Citation tags are never shared with other accounts.
