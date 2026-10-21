---
appliesTo:
- type: entity
  id: citation
- type: entity
  id: citation-tag
references:
- kind: code
  role: implementation
  target: src/server/routes/citations.ts#registerCitationRoutes
---

# Personal citation keys are unique and edits use the inspected revision

Keys and citation-tag names are compared without case. Updating content or assignments requires the last-read revision and advances it; saving an updated reference from source preserves its tags unless replacements are supplied.
