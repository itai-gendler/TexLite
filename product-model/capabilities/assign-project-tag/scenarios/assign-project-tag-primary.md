---
kind: primary
routes:
  web: Browser
steps:
- text: The person selects another tag for the project
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite saves the project tag in this person's project organization
  kind: product
  entities:
  - entity: project-organization
    effect: changes
    facts:
    - Tags
  - entity: project-tag
    effect: reads
    facts:
    - Name
    - Color
    - Project count
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Assign project tag

## Trigger

The person opens Tags for a project and selects one of their tags.

## Outcome

The project shows the tag and appears under that tag's filter for this person only.
