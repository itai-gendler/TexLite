---
entities:
- entity: snapshot
  shows:
  - Created
  - Author
  - Reason
  - Label
  - Changed paths
  - Files
  - Compiler settings
  - Storage
  collects:
  - Label
- entity: selection-history
  shows:
  - File path
  - Contributors
  - Time
  - Operation
  - Passage
  - Boundary
  - Storage
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
- entity: project
  shows:
  - Name
  - Icon
  - Owner
  - Main document
  - Engine
  - Latexmkrc
  - ChkTeX enabled
  - Modified
  - Created
references:
- kind: code
  role: implementation
  target: src/client/HistoryDialog.tsx
- kind: code
  role: implementation
  target: src/client/SelectionHistoryDialog.tsx
---

# History

A project's snapshots and the edit history of a selected passage: what changed, who changed it, and when, with comparison and restore.
