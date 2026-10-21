---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/commentMentions.ts
- kind: code
  role: implementation
  target: src/client/workspace/MentionTextarea.tsx
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
domain: comments
---

# Mention participant

Notify another active participant by including their exact username in a comment or reply.
