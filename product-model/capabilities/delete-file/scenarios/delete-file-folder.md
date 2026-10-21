---
kind: alternate
routes:
  web: Browser
steps:
- text: The person confirms deletion
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite removes the folder and its source contents
  kind: product
  entities:
  - entity: folder
    effect: removes
  - entity: file
    effect: removes
  - entity: attachment
    effect: removes
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Delete a folder and contents

## Trigger

The person confirms deleting a folder.

## Outcome

The folder and its contents are removed.
