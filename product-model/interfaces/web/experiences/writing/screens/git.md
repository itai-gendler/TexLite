---
entities:
- entity: git-repository
  shows:
  - Remote
  - Name
  - Visibility
  - Branch
  - Default branch
  - Changes
  - Pushed
  collects:
  - Name
  - Visibility
- entity: git-commit
  shows:
  - Revision
  - Message
  - Author
  - Time
  - Difference
  collects:
  - Message
- entity: file
  shows:
  - Path
  - Content
  - Size
  - Language
- entity: attachment
  shows:
  - Path
  - Content
  - Size
  - Preview type
references:
- kind: code
  role: implementation
  target: src/client/GitDialog.tsx
---

# Git

Inspect the selected project’s working tree, commits, and backup destination.
