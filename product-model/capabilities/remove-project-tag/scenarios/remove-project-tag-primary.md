---
kind: primary
routes:
  web: Browser
steps:
- text: The person removes a tag from the project
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite removes the project tag from this person's project organization
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

# Remove project tag

## Trigger

The person opens Tags for a project and removes one of its tags.

## Outcome

The project no longer shows the tag for this person; the tag itself stays.
