# Survey Before Building

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** I'm about to write code, propose architecture, or add new files in a repo

---

## Outline (to expand when this protocol gets written)

WHEN: opening a repo I haven't seen recently OR proposing new file/feature.
THEN: ls (dir structure) + git log --oneline -20 (recent activity) + grep for relevant terms + read existing docs/state.md + check gh pr list. THEN propose.
NEVER: assume directory structure or file purpose from name alone.

## Example slot

Almost duplicated jarvis/scripts/analyze-virality.py (2026-05-22): was about to write extract-features.py from scratch before noticing 21 existing Python scripts. Saved by late ls.

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
