---
entities:
- entity: project-tag
  shows:
  - Name
  - Color
  - Project count
  collects:
  - Name
  - Color
references:
- kind: code
  role: implementation
  target: src/client/pages/TagManagementDialog.tsx
---

# Project tags

Where a person creates, renames, recolors and deletes their project tags, with how many projects use each.
