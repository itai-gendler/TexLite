---
appliesTo:
- type: entity
  id: compile-job
  effect: changes
references:
- kind: code
  role: implementation
  target: src/server/routes/compile.ts#registerCompileRoutes
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
- unattended: true
---

# Only the owner and Read & write members run and stop compiles; TexLite ends interrupted ones

Read only members cannot start or cancel a compile. When TexLite restarts, compiles that had not finished are ended, and a PDF that was already published stays available.
