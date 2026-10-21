---
kind: primary
routes:
  web: Browser
steps:
- text: The person confirms deleting the tag
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::tags
  actor: user
- text: TexLite deletes the project tag
  kind: product
  entities:
  - entity: project-tag
    effect: removes
  contexts:
    web:
      place: web::writing::tags
  actor: user
---

# Delete project tag

## Trigger

The person no longer needs a project tag.

## Outcome

The tag disappears from every project it was on; the projects stay.
