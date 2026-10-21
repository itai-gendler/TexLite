---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/projectMembers.ts#registerProjectMemberRoutes
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
- kind: code
  role: implementation
  target: src/client/workspace/WorkspaceDialogs.tsx
---

# Remove member

Remove the membership and notify the participant’s open sessions that sharing has ended.
