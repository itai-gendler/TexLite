---
kind: primary
routes:
  web: Browser
steps:
- text: The person changes an editor setting in the project settings
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite saves the editor preferences in this browser for this person and project
  kind: product
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: editor-preferences
    effect: changes
    facts:
    - Vim mode
    - Spelling assistance
    - Format before compile
    - Formatter options
    - Open files in tabs
    - Math preview
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Change editor settings

## Trigger

The person turns on Vim keybindings, tabs, math preview or format before compiling, or changes the tex-fmt options.

## Outcome

The editor follows the new settings at once. They apply only to this person, in this browser and project, and never to other participants.
