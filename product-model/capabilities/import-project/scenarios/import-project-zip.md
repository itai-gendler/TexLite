---
kind: primary
routes:
  web: Browser
steps:
- text: The person selects an archive
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite creates the project and extracted files
  kind: product
  entities:
  - entity: project
    effect: creates
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
    - Active sessions
  - entity: file
    effect: creates
    facts:
    - Path
    - Content
    - Size
    - Language
    with: project
  - entity: attachment
    effect: creates
    facts:
    - Path
    - Content
    - Size
    - Preview type
    with: project
  - entity: folder
    effect: creates
    facts:
    - Path
    with: project
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite opens the imported project
  kind: product
  entities:
  - entity: project
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Import a ZIP project

## Trigger

A person selects a ZIP archive and optional project name.

## Outcome

The extracted project opens with the detected root and default compiler engine; project latexmkrc selection starts empty.
