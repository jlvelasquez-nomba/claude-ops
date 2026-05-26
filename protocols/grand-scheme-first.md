# Grand Scheme First

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** About to design or implement a feature without first sketching the big picture

---

## Outline (to expand when this protocol gets written)

WHEN: user asks for a feature/component/endpoint.
THEN: before code, sketch (in chat): what's the user-visible outcome? what layers does it touch? where does data flow? what's the smallest E2E version? what gets cut for v1?
NEVER: start with the prettiest feature. always start with the skeleton that proves the data path works.

## Example slot

extract-features.py 2026-05-22: jumped to 'let me code the extractor' before sketching how features would actually feed the KNN. Resulted in feature vector that mostly mapped 1:1 to fields, no real downstream design.

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
