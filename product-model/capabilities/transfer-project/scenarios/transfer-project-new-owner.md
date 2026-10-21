---
kind: primary
routes:
  web: Browser
steps:
- text: The person confirms the recipient
  kind: actor
  entities: []
  contexts:
    web:
      place: web::writing::projects
  actor: user
- text: TexLite changes project ownership and retains the previous owner’s membership
  kind: product
  entities:
  - entity: project
    effect: changes
    facts:
    - Owner
    - Modified
  - entity: membership
    effect: creates
    facts:
    - Role
    - Member
  contexts:
    web:
      place: web::writing::projects
  actor: user
---

# Transfer ownership and keep editing

## Trigger

The current owner selects another active account.

## Outcome

The recipient becomes owner and the previous owner remains a Read & write member. Existing personal GitHub credentials stay with their accounts.

## Edge cases

- Choosing oneself is rejected.
- A disabled or deleted recipient cannot be selected.
- If the recipient was a shared member, that membership is absorbed into ownership.
