---
kind: primary
routes:
  web: Browser
steps:
- text: The person opens an item in the file tree
  kind: actor
  entities:
  - entity: file
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite opens the file in the editor or previews the attachment
  kind: product
  entities:
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

# Browse files

## Trigger

The person works through the project's source tree.

## Outcome

Text files open in the editor; images and PDFs open in a preview, and other attachments offer a download.
