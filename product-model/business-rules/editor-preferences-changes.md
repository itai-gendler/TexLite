---
appliesTo:
- type: entity
  id: editor-preferences
  effect: changes
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

# Only the person they belong to changes their editor settings

Editor settings are kept in the person's own browser, separately for each project.
