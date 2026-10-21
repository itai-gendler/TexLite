---
appliesTo:
- type: entity
  id: collaboration-session
  effect: changes
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
permits:
- related:
  - verb: holds
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
- related:
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
---

# Participants update their own presence; owners update others' access

A participant's own session follows their active file and cursor. When the owner changes a member's access, TexLite updates that member's open sessions.
