---
kind: edge
routes:
  web: Browser
steps:
- text: The person requests formatting
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports that source changed
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Discard a stale formatting result

## Trigger

The source changes while formatting is being computed.

## Outcome

The stale replacement is discarded and the person can try again against current text.

## Edge cases

- Formatter failure reports an error without replacing source.
