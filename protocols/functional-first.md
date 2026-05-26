# Functional First (over pretty)

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** Building UX while backend/API/data layer isn't proven

---

## Outline (to expand when this protocol gets written)

WHEN: about to style / polish UI / improve visuals.
THEN: confirm: does the E2E happy path WORK first? if no, ugly-but-functional > pretty-but-broken. style is the LAST step.
NEVER: ship pretty button that doesn't trigger anything real. it's worse than no button (sets wrong expectation).

## Example slot

Hypothetical (operator's brief #4): SaaS booking 23 attempts. UX polished, backend broken, neither shipped. Functional-first protocol prevents this.

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
