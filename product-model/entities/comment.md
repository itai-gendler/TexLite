---
domain: comments
relations:
- entity: reply
  verb: contains
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
- kind: code
  role: implementation
  target: src/server/anchors.ts
---

# Comment

A source-anchored discussion thread.

## Information kept

- **Content** — The top-level message.
- **Author** — The person who wrote it, or Deleted User.
- **File path** — The file containing the annotated passage.
- **Quote** — The currently attached passage or last attached quote.
- **Anchor** — Its source position and attached or orphaned condition.
- **Created** — When the thread began.
- **Edited** — When its message was last edited.
- **Resolution** — Who resolved it and when; empty when open.

## States

### Open

The discussion needs review.

### Resolved

The discussion has been resolved.
