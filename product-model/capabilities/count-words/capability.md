---
availability:
- place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/routes/wordCount.ts#registerWordCountRoutes
- kind: code
  role: implementation
  target: src/server/texcount.ts
- kind: code
  role: implementation
  target: src/client/workspace/WordCountDialog.tsx
---

# Count words

Use optional host TeXcount for the selected document or a selected source passage.
