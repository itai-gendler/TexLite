---
appliesTo:
- type: entity
  id: collaboration-session
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
permits:
- related:
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: user
  when:
  - entity: project
    fact: Active sessions
    under: 10
- related:
  - verb: contains
    entity: project
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
  when:
  - entity: project
    fact: Active sessions
    under: 10
- related:
  - verb: contains
    entity: project
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: user
  when:
  - entity: project
    fact: Active sessions
    under: 10
- related:
  - verb: contains
    entity: project
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
  when:
  - entity: project
    fact: Active sessions
    under: 10
---

# Only the owner and members join a project's live workspace, up to ten sessions

Anyone the project is shared with can open its workspace while fewer than ten sessions are active or joining.
