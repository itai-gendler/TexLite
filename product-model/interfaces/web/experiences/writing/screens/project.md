---
entities:
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
  - Active sessions
  collects:
  - Name
  - Main document
  - Engine
  - Latexmkrc
  - ChkTeX enabled
- entity: file
  shows:
  - Path
  - Content
  - Size
  - Language
  collects:
  - Path
  - Content
- entity: attachment
  shows:
  - Path
  - Content
  - Size
  - Preview type
- entity: folder
  shows:
  - Path
  collects:
  - Path
- entity: membership
  shows:
  - Role
  - Member
  collects:
  - Member
  - Role
- entity: collaboration-session
  shows:
  - Participant
  - Permission
  - Active file
  - Cursor
  - Connection
- entity: compile-job
  shows:
  - Root
  - Requested by
  - Requested
  - Finished
  - Log
  - Diagnostics
  - PDF
  - Artifacts
  - Source freshness
  - Cache available
- entity: comment
  shows:
  - Content
  - Author
  - File path
  - Quote
  - Anchor
  - Created
  - Edited
  - Resolution
  collects:
  - Content
- entity: reply
  shows:
  - Content
  - Author
  - Created
  - Edited
  collects:
  - Content
- entity: mention
  shows:
  - Target
  - Sender
  - Created
  - Read reason
- entity: editor-preferences
  shows:
  - Vim mode
  - Spelling assistance
  - Format before compile
  - Formatter options
  - Open files in tabs
  - Math preview
  collects:
  - Vim mode
  - Spelling assistance
  - Format before compile
  - Formatter options
  - Open files in tabs
  - Math preview
- entity: dictionary-word
  shows:
  - Word
  collects:
  - Word
- entity: citation
  shows:
  - Key
  - Entry type
  - BibTeX
  - Title
  - Authors
  - Year
  - Tags
  - Revision
  - Modified
- entity: deployment
  shows:
  - Project latexmkrc allowed
  - Allowed engines
  - Upload limit
references:
- kind: code
  role: implementation
  target: src/client/pages/ProjectWorkspace.tsx
---

# Project workspace

One project’s source, review discussions, collaboration, compiler settings, and output.
