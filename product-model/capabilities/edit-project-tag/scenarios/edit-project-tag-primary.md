---
kind: primary
routes:
  web: Browser
steps:
- text: The person changes the tag's name or color
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::tags
  actor: user
- text: TexLite saves the project tag
  kind: product
  entities:
  - entity: project-tag
    effect: changes
    facts:
    - Name
    - Color
    - Project count
  contexts:
    web:
      place: web::writing::tags
  actor: user
---

# Edit project tag

## Trigger

A project tag needs a better name or color.

## Outcome

Every project carrying the tag shows its new name and color for this person.
