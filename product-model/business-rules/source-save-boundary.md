---
appliesTo:
- type: entity
  id: file
- type: entity
  id: compile-job
- type: capability
  id: download-project
- type: capability
  id: duplicate-project
references:
- kind: code
  role: implementation
  target: src/server/projectMutations.ts#ProjectMutationCoordinator
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
---

# Source operations consume successfully saved live content

Compilation, export, duplication, and source replacements save current edits before consuming source. Unsuccessful persistence reports a retryable failure instead of continuing with older saved text.
