---
appliesTo:
- type: entity
  id: mention
  effect: reads
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
permits:
- related:
  - verb: receives
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: receives
    entity: account
  - verb: uses
    entity: administrator
---

# Only its recipient sees a mention

Each person sees only the mentions addressed to them.
