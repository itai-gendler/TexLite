---
kind: edge
routes:
  web: Browser
steps:
- text: The person inspects writing assistance
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite reports the unavailable assistance
  kind: product
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Continue when writing tools are unavailable

## Trigger

Harper or ChkTeX cannot complete a check.

## Outcome

The workspace remains usable; Harper falls back to native browser English spellchecking, and unavailable ChkTeX diagnostics are reported separately.
