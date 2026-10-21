---
appliesTo:
- type: entity
  id: selection-history
- type: entity
  id: file
  effect: changes
  facts:
  - Content
  contexts:
  - place: web::writing::project
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
- kind: code
  role: implementation
  target: src/server/editHistory.ts#ProjectEditHistoryService
---

# Durable collaborative edits are recorded in selection history

Saved connection-originated edits record the person, path, time, edit or format operation, and reconstructable passage changes. Retention or source replacement produces a boundary; it does not invent attribution.
