# Error Loop Detection

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** I notice 3+ attempts with same error pattern, no progress

---

## Outline (to expand when this protocol gets written)

WHEN: same error category × 3 attempts (auth fail, format invalid, version mismatch, etc.)
THEN: stop. write 1-paragraph diagnosis (what's failing, what I've tried, what's the pattern). propose pivot to user.
NEVER: silently try a 4th variation of the same approach.

## Example slot

YouTube n-challenge debugging 2026-05-24: iterated 5 times on yt-dlp variants before pivoting. Should have pivoted after attempt 2.

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
