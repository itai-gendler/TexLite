---
appliesTo:
- type: entity
  id: project
  effect: reads
references:
- kind: code
  role: implementation
  target: src/server/projects.ts#accessibleProject
permits:
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: administrator
- related:
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
---

# Only the owner and members see a project

A project appears in the catalogs of its owner and the people it is shared with, and nobody else, administrators included.
