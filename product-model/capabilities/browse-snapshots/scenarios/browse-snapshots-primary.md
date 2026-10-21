---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens Snapshots in the workspace
  kind: actor
  entities:
  - entity: snapshot
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::history
  actor: user
- text: TexLite lists the snapshots newest first, with older ones loaded on request
  kind: product
  entities:
  - entity: snapshot
    effect: reads
    facts:
    - Created
    - Author
    - Reason
    - Label
    - Changed paths
    - Files
    - Compiler settings
    - Fingerprint
    - Storage
  contexts:
    web:
      place: web::writing::history
  actor: user
---

# Browse history

## Trigger

The person looks for an earlier state of the project.

## Outcome

Each snapshot shows when it was taken, why, who made it when there is a single author, its label and its changed files. The owner also sees the snapshots' storage use.
