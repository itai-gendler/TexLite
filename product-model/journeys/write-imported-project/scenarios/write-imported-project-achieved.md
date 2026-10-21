---
kind: primary
result: achieved
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
  capability: import-project
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
  capability: import-project
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
  capability: import-project
- text: The person edits file content
  kind: actor
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
  contexts:
    web:
      place: web::writing::project
  actor: user
  capability: edit-file
- text: TexLite saves the file and remaps comment anchors
  kind: product
  entities:
  - entity: file
    effect: changes
    facts:
    - Content
    - Size
  - entity: comment
    effect: changes
    facts:
    - Anchor
    - Quote
  contexts:
    web:
      place: web::writing::project
  actor: user
  capability: edit-file
---

# Write in an imported project

## Trigger

The person uploads a ZIP archive from Projects.

## Outcome

The new workspace is open and the first source edit is saved.
