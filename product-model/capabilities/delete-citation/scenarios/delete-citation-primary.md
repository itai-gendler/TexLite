---
kind: primary
routes:
  web: Browser
steps:
- text: The person confirms deleting the citation
  kind: actor
  entities:
  - entity: citation
    effect: reads
    facts: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
- text: TexLite deletes the citation from the library
  kind: product
  entities:
  - entity: citation
    effect: removes
  contexts:
    web:
      place: web::writing::citations
  actor: user
---

# Delete citation

## Trigger

The person no longer needs a saved reference.

## Outcome

The citation is gone from the library. Projects that already contain its BibTeX are unchanged.
