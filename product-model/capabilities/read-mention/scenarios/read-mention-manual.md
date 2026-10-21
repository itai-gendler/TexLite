---
kind: alternate
routes:
  web: Browser
steps:
- text: The person marks one mention, or all mentions in the project, as read
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: mention
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite marks the mention records read
  kind: product
  entities:
  - entity: mention
    effect: changes
    from: Unread
    to: Read
    facts:
    - Read reason
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Mark mentions read explicitly

## Trigger

The person marks one notification or all project notifications read.

## Outcome

The chosen notifications become read with a manual acknowledgement.
