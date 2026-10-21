---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses Reopen on a resolved comment
  kind: actor
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reopens the comment and clears who resolved it and when
  kind: product
  entities:
  - entity: comment
    effect: changes
    from: Resolved
    to: Open
    facts:
    - Resolution
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Reopen comment

## Trigger

A resolved point turns out to need more discussion.

## Outcome

The thread returns to Open. Previously read mentions remain read.
