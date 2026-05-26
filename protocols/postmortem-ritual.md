# Postmortem Ritual

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** Something broke unexpectedly OR a session had a notable failure mode

---

## Outline (to expand when this protocol gets written)

WHEN: a debug took >30 min, OR something broke that should have been caught, OR a fabrication was caught.
THEN: write 5-line postmortem: (1) what happened, (2) root cause, (3) fix applied, (4) what would have caught it earlier, (5) what changes in claude-ops (new anti-pattern? new protocol clause? doctor.sh check?).
NEVER: just fix and move on without the writeup. Knowledge evaporates.

## Example slot

YouTube n-challenge 2026-05-24: 1h debugging, no postmortem written. The learning ('detect upstream blocker after 2 tries') didn't get codified anywhere until this very repo was created.

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
