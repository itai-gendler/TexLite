---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens Manage tags
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::tags
  actor: user
- text: TexLite lists the person's project tags and how often each is used
  kind: product
  entities:
  - entity: project-tag
    effect: reads
    facts:
    - Name
    - Color
    - Project count
  contexts:
    web:
      place: web::writing::tags
  actor: user
---

# Browse project tags

## Trigger

The person wants to tidy the tags they use for projects.

## Outcome

Only this person's project tags are listed, ready to rename, recolor or delete.
