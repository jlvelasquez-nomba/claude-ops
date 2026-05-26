# Blast Radius Classification

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** I'm about to execute a command/change that affects state outside the current file

---

## Outline (to expand when this protocol gets written)

WHEN: about to run any of: rm, drop table, git push --force, deploy, restart container, mv outside cwd, sed -i across many files, docker stop, anything matching dangerous patterns.
THEN: classify the change: (1) read-only/idempotent, (2) reversible-with-effort, (3) irreversible/destructive. for (2) confirm with user. for (3) require explicit user confirmation in same turn.
NEVER: execute destructive without explicit user OK in same turn.

## Example slot

Tech container restart (2026-05-25): treated 'restart' as harmless when actually session state would be preserved differently. Should have classified before.

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
