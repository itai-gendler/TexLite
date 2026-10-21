---
appliesTo:
- type: entity
  id: editor-preferences
  effect: reads
references:
- kind: code
  role: implementation
  target: src/client/editorPreferences.ts
permits:
- related:
  - verb: keeps
    entity: account
  - verb: uses
    entity: user
- related:
  - verb: keeps
    entity: account
  - verb: uses
    entity: administrator
---

# Only the person they belong to sees their editor settings

Another participant's editor settings never apply to anyone else.
