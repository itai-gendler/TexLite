---
kind: primary
routes:
  web: Browser
steps:
- text: The person enters a name
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite creates the project and its starter file
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
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite opens the new project workspace
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

# Create a starter project

## Trigger

A person supplies a project name.

## Outcome

The new project uses the deployment’s default engine and opens in its workspace.

## Edge cases

- An empty name or one longer than 120 characters is rejected.
