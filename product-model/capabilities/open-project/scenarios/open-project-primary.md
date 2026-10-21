---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens a project from Projects or its link
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite opens the project with its file tree and main document
  kind: product
  entities:
  - entity: project
    effect: reads
    facts:
    - Name
    - Icon
    - Owner
    - Main document
    - Engine
    - Latexmkrc
    - ChkTeX enabled
    - Modified
    - Created
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
      place: web::writing::project
  actor: user
---

# Open project

## Trigger

The person goes back to a project they own or that is shared with them.

## Outcome

The workspace shows the source and retained result for the selected root. Joining live collaboration is attempted as it opens.
