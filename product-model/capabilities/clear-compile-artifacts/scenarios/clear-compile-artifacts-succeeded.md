---
kind: primary
routes:
  web: Browser
steps:
- text: The person confirms cleanup
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::project
  actor: user
- text: TexLite removes the compile job and its artifacts
  kind: product
  entities:
  - entity: compile-job
    effect: removes
    from: Succeeded
  contexts:
    web:
      place: web::writing::project
  actor: user
---

# Clear succeeded output

## Trigger

The person confirms clearing output for the selected root.

## Outcome

Completed results and output for this root are cleared; the PDF is no longer retained.

## Edge cases

- Cleanup is serialized against active compiles and refuses when the target remains busy.
