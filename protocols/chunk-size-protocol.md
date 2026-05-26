# Chunk Size Protocol

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** About to generate >200 lines of code in a single output

---

## Outline (to expand when this protocol gets written)

WHEN: about to write a large script, complex refactor, or many files.
THEN: split into chunks <200 lines. between chunks, VERIFY each works (run test, eyeball diff, ask for OK). then next chunk.
NEVER: dump 500-line script in one shot and assume it works. ('time bombs hidden in code that aren't apparent during review' — HN thread 2026-05-25).

## Example slot

build-ambassadors.py first version 2026-05-22: 226 lines single-shot with instaloader. Failed on first run. Should have written + tested in 3 chunks of ~75 lines.

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
