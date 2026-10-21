---
appliesTo:
- type: entity
  id: attachment
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/routes/projectFiles.ts#registerProjectFileRoutes
permits:
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
  - entity: membership
    fact: Role
    is: Read & write
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
  - entity: membership
    fact: Role
    is: Read & write
---

# Only the project owner and members with Read & write access upload attachments

Read only members cannot add images, PDFs or other resources to the source tree.
