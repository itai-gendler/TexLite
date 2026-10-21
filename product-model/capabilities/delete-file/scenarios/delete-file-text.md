---
kind: primary
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
- text: TexLite removes the file and its comments
  kind: product
  entities:
  - entity: file
    effect: removes
  - entity: comment
    effect: removes
    from: Open
    with: file
    as: open-comment
  - entity: comment
    as: resolved-comment
    effect: removes
    from: Resolved
    with: file
  - entity: reply
    as: open-reply
    effect: removes
    with: open-comment
  - entity: reply
    as: resolved-reply
    effect: removes
    with: resolved-comment
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Delete a text file

## Trigger

The person confirms deleting a source file.

## Outcome

The file and its attached discussions disappear from the project. Removing the selected latexmkrc clears that selection.

## Edge cases

- The configured main document and a folder containing it cannot be deleted.
