# Layer by Layer

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** Building a user-facing surface (UI, dashboard, app)

---

## Outline (to expand when this protocol gets written)

WHEN: building anything that has multiple layers (db → backend → middleware → frontend).
THEN: build LAYER 1 (data + planning) first, prove it works E2E. then layer 2, prove it works integrated with 1. etc.
NEVER: build all layers in parallel hoping they 'click together at the end'. they don't.

## Example slot

Hypothetical (operator's brief #3): SaaS booking shotgun pattern. Buttons render but backend doesn't connect. Avoid by enforcing layer-by-layer.

## Format reference

Full content follows the structure of [no-fabrication.md](./no-fabrication.md):
- What this rule says (to me, Claude)
- What to do when [trigger]
- Concrete examples from my own real sessions (both ✅ and ❌)
- Detection signals (am I violating this?)
- What this DOES NOT mean
- Enforcement loop
- Interaction with other protocols

> When a failure mode in this category hits in a session, EXPAND this stub with the case study and finalize the protocol. Then continue with the work.
