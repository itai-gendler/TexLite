---
appliesTo:
- type: entity
  id: citation-tag
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

# Only its owner renames or recolors a citation tag

Citation tags are private to the account that created them.
