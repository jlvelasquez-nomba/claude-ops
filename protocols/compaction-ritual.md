# Compaction Ritual

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** Conversation context growing (>50 messages or sense of bloat)

---

## Outline (to expand when this protocol gets written)

WHEN: long session, context feels heavy, signs of model degradation (slower, more confused).
THEN: propose summary of decisions made + open threads + dropped context. user confirms summary, we continue with compacted state.
NEVER: silently let context degrade until session crashes (see Tech bot 2026-05-25, 75K tokens).

## Example slot

Tech container crash 2026-05-25: 147 messages, 75K tokens, OpenAI quota exhausted. Should have compacted at message ~80.

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
