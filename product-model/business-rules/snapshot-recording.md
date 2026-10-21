---
appliesTo:
- type: entity
  id: snapshot
  effect: creates
references:
- kind: code
  role: implementation
  target: src/server/history.ts#ProjectHistoryService
permits:
- unattended: true
---

# TexLite records a snapshot after every saved file change

Snapshots are taken automatically; nobody creates one by hand.
