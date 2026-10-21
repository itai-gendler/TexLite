---
appliesTo:
- type: entity
  id: compile-job
  effect: reads
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
- related:
  - verb: contains
    entity: project
  - verb: contains
    entity: membership
  - verb: holds
    entity: account
  - verb: uses
    entity: administrator
---

# Only the owner and members see a project's compile output

Everyone in the project, Read only members included, sees the latest status, log, diagnostics and retained PDF.
