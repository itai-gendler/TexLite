---
kind: edge
routes:
  web: Browser
steps:
- text: The person saves an inspected reference
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
- text: TexLite reports the revision conflict
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::citations
  actor: user
---

# Keep a newer library edit

## Trigger

Another browser saved a newer revision first.

## Outcome

The stale save is refused and the person must refresh before editing again.
