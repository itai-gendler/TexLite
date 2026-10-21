---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
- kind: code
  role: implementation
  target: src/server/commentMentions.ts
- kind: code
  role: implementation
  target: src/client/workspace/useProjectMentions.ts
domain: comments
---

# Read mention

Open a mention target or explicitly mark one or all project mentions read.
