---
kind: primary
routes:
  web: Browser
steps:
- text: The person supplies the reference
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
- text: TexLite saves the citation and opens its tag editor
  kind: product
  entities:
  - entity: citation
    effect: creates
    facts:
    - Key
    - Entry type
    - BibTeX
    - Title
    - Authors
    - Year
    - Tags
    - Revision
    - Modified
  contexts:
    web:
      place: web::writing::citations
  actor: user
---

# Save a new library entry

## Trigger

The person supplies a complete BibTeX entry.

## Outcome

The personal citation retains its original text and extracted metadata. Its tag editor opens for immediate organization.

## Edge cases

- The browser rejects malformed, oversized, or multiple-entry input where one entry is required.
- An existing citation key is reported as a conflict.
