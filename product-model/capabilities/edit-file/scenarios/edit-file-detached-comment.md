---
kind: alternate
routes:
  web: Browser
steps:
- text: The person replaces file content
  kind: actor
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite marks the comment anchor orphaned
  kind: product
  entities:
  - entity: comment
    effect: changes
    facts:
    - Anchor
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Keep a discussion after its passage is replaced

## Trigger

A person replaces or deletes an entire annotated passage.

## Outcome

The discussion becomes orphaned and keeps its last attached quote; restoring the full quote with matching context can reattach it.
