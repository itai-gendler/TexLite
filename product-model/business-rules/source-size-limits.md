---
appliesTo:
- type: entity
  id: file
- type: entity
  id: attachment
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
- kind: code
  role: implementation
  target: src/server/routes/projectFiles.ts#registerProjectFileRoutes
- kind: code
  role: implementation
  target: src/server/zip.ts
---

# Collaborative text and uploads respect their applicable limits

Collaborative text is limited to the smaller of 5 MiB and the deployment upload limit. Other uploads use the configured limit. ZIP import also enforces entry-count and expanded-total limits.
