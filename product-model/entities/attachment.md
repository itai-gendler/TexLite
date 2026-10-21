---
references:
- kind: code
  role: implementation
  target: src/server/routes/projectFiles.ts#registerProjectFileRoutes
- kind: code
  role: implementation
  target: src/client/workspace/useProjectFiles.ts
---

# Attachment

A source resource opened for preview or download rather than collaborative editing, such as an image, PDF, or other text/data format.

## Information kept

- **Path** — Its location and name in the source tree.
- **Content** — The uploaded bytes.
- **Preview type** — Image, PDF, read-only text, or download-only resource.
- **Size** — Its byte size.
