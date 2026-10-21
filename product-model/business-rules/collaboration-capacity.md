---
appliesTo:
- type: entity
  id: collaboration-session
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
---

# A project admits at most ten collaboration sessions

The limit counts active and pending sessions, including separate browser sessions from the same person.
