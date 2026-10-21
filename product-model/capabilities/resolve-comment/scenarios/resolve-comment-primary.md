---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses Resolve on an open comment
  kind: actor
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite resolves the comment, recording who resolved it and when
  kind: product
  entities:
  - entity: comment
    effect: changes
    from: Open
    to: Resolved
    facts:
    - Resolution
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Resolve comment

## Trigger

A discussion has been dealt with.

## Outcome

The thread is Resolved and existing unread mentions in it become read. Repeating resolution keeps the original attribution.
