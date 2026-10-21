---
kind: primary
routes:
  web: Browser
steps:
- text: The person searches, picks a tag, switches between Active and Archived, or changes the sort
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite lists the matching projects with their owner, dates, the person's project tags and unread mentions
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
  - entity: project-organization
    effect: reads
    facts:
    - Archived
    - Tags
  - entity: project-tag
    effect: reads
    facts:
    - Name
    - Color
    - Project count
  - entity: mention
    effect: reads
    facts:
    - Target
    - Sender
    - Created
    - Read reason
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Browse projects

## Trigger

The person signs in and lands on Projects, or returns to it.

## Outcome

The person sees the projects they own or that are shared with them, in their own active or archived list, ordered by last modified or created.
