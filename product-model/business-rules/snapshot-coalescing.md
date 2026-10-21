---
appliesTo:
- type: entity
  id: snapshot
  effect: changes
  facts:
  - Files
  - Compiler settings
  - Changed paths
  - Author
  - Fingerprint
references:
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
permits:
- unattended: true
---

# Automatic saves within two minutes share one snapshot

While the latest snapshot is an unlabeled automatic save less than two minutes old, the next automatic save updates it instead of adding another; a snapshot with mixed contributors has no single author.
