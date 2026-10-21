---
kind: primary
routes:
  web: Browser
steps:
- text: The person chooses the current file or the whole project, and filters
  kind: actor
  entities:
  - entity: project
    effect: reads
    facts: []
  - entity: file
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite shows the matching comments with their replies in order
  kind: product
  entities:
  - entity: comment
    effect: reads
    facts:
    - Content
    - Author
    - File path
    - Quote
    - Anchor
    - Created
    - Edited
    - Resolution
  - entity: reply
    effect: reads
    facts:
    - Content
    - Author
    - Created
    - Edited
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Browse comments

## Trigger

The person opens the comments panel to review discussions.

## Outcome

Review can filter Open or Resolved threads, participants, top-level authors versus reply authors, and unread mentions, and sort by source position or newest first. Explicit source navigation can reveal a target outside those filters.
