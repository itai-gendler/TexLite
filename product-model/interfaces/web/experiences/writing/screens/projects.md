---
entities:
- entity: project
  shows:
  - Name
  - Icon
  - Owner
  - Modified
  - Created
  collects:
  - Name
  - Icon
  - Owner
- entity: project-organization
  shows:
  - Archived
  - Tags
  collects:
  - Archived
  - Tags
- entity: project-tag
  shows:
  - Name
  - Color
  - Project count
- entity: mention
  shows:
  - Target
  - Sender
  - Created
  - Read reason
references:
- kind: code
  role: implementation
  target: src/client/pages/Dashboard.tsx
---

# Projects

The person's project catalog: their active or archived projects with owner, dates, tags and unread mentions, where projects are created, imported and managed.
