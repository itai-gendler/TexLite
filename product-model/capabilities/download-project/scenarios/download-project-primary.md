---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses Download in the project's actions
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite saves pending edits and returns a ZIP of the project's files and folders
  kind: product
  entities:
  - entity: project
    effect: reads
    facts:
    - Name
  - entity: file
    effect: reads
    facts:
    - Path
    - Content
    - Size
  - entity: attachment
    effect: reads
    facts:
    - Path
    - Content
    - Size
  - entity: folder
    effect: reads
    facts:
    - Path
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Download project

## Trigger

The person wants a copy of the project's source.

## Outcome

The ZIP holds the source as last saved, including the edits that were still pending.
