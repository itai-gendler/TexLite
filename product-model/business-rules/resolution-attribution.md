---
appliesTo:
- type: entity
  id: comment
  facts:
  - Resolution
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
---

# A comment keeps the attribution of its current resolution

An actual Open-to-Resolved change records the resolver and time. Repeating it preserves that attribution. Reopening clears it; removed accounts appear as Deleted User.
