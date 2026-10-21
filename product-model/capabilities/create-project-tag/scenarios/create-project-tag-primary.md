---
kind: primary
routes:
  web: Browser
steps:
- text: The person enters a tag name and picks a color
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::tags
  actor: user
- text: TexLite creates the project tag
  kind: product
  entities:
  - entity: project-tag
    effect: creates
    facts:
    - Name
    - Color
    - Project count
  contexts:
    web:
      place: web::writing::tags
  actor: user
---

# Create project tag

## Trigger

The person wants a new way to group their projects.

## Outcome

The tag is available for this person's projects only.
