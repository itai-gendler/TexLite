---
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
- kind: code
  role: implementation
  target: src/client/workspace/useProjectCollaboration.ts
---

# Collaboration session

One open browser workspace participating in a project.

## Information kept

- **Participant** — The signed-in person.
- **Permission** — The current project access.
- **Active file** — The source file being visited.
- **Cursor** — The participant’s current source position.
- **Connection** — Connecting, connected, disconnected, or waiting to reconnect.
