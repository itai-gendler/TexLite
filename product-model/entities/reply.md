---
domain: comments
references:
- kind: code
  role: implementation
  target: src/server/routes/comments.ts#registerCommentRoutes
---

# Reply

A separately editable response in a comment thread.

## Information kept

- **Content** — The response text.
- **Author** — The writer, or Deleted User.
- **Created** — When it was posted.
- **Edited** — When it was last edited.
