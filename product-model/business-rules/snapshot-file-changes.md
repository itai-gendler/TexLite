---
appliesTo:
- type: entity
  id: snapshot
references:
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
---

# A snapshot is added only when files change

Changing only the compiler settings adds no snapshot; the effective settings are kept with the next snapshot that has a file change.
