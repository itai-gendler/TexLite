---
kind: primary
routes:
  web: Browser
steps:
- text: The owner enters a new name
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite saves the project name
  kind: product
  entities:
  - entity: project
    effect: changes
    facts:
    - Name
    - Modified
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Rename project

## Trigger

The owner chooses Rename in the project's actions.

## Outcome

Everyone the project is shared with sees the new name. An empty name, or one over 120 characters, is refused.
