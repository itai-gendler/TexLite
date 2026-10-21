---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens their mentions in the workspace
  kind: actor
  entities:
  - entity: mention
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite lists this person's mentions with who sent them and where
  kind: product
  entities:
  - entity: mention
    effect: reads
    facts:
    - Target
    - Sender
    - Created
    - Read reason
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Browse mentions

## Trigger

Projects shows that the person has unread mentions in a project.

## Outcome

The person sees each mention addressed to them, unread first, with the discussion it points to.
