---
appliesTo:
- type: entity
  id: collaboration-session
  effect: removes
  contexts:
  - place: web::writing
references:
- kind: code
  role: implementation
  target: src/server/collaboration.ts#CollaborationService
- kind: code
  role: implementation
  target: src/server/routes/users.ts#registerUserManagementRoutes
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

# Participants leave their own sessions; owners end a removed member's sessions

Closing the workspace ends a person's own session. Removing a member ends that member's open sessions in the project.
