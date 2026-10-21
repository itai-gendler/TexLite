---
references:
- kind: code
  role: implementation
  target: src/server/routes/projectFiles.ts#registerProjectFileRoutes
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
relations:
- entity: comment
  verb: anchors
  cardinality: one-to-many
---

# File

An editable text source or data file in a project.

## Information kept

- **Path** — Its location and name in the source tree.
- **Content** — Its current text.
- **Language** — The editable source language selected from the filename.
- **Size** — Its byte size.
