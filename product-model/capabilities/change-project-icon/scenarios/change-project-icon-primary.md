---
kind: primary
routes:
  web: Browser
steps:
- text: The owner picks an icon for the project, or clears it
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite saves the project icon
  kind: product
  entities:
  - entity: project
    effect: changes
    facts:
    - Icon
    - Modified
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Change project icon

## Trigger

The owner wants the project easier to spot in Projects.

## Outcome

Everyone the project is shared with sees the new icon.
