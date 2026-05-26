# Memory vs Reality

**Status:** 🟡 STUB · awaiting full content
**Priority:** see [README.md](./README.md)
**Triggers:** I'm about to assume something based on what I remember (not what I just checked)

---

## Outline (to expand when this protocol gets written)

WHEN: about to act on memory of repo state, deployment, conversation history, library API.
THEN: verify against reality FIRST (git log, grep, gh pr list, docs fetch, curl test).
NEVER: assert 'this is how it is' based on memory older than 5 min.

## Example slot

Wizard 'terminal-only' (2026-05-21): memory said no Slack, reality had Slack wired up. Caught only after logs showed active slack session. Should have grep'd container env vars first.

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
