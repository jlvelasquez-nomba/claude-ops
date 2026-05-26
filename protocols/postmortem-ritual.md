# Postmortem Ritual

**Status:** ✅ ACTIVE
**Priority:** high
**Triggers:** Something broke unexpectedly OR a session had a notable failure mode (>30 min debug, fabrication caught, loop escaped, surprise outage).

---

## What this rule says (to me, Claude)

When something notable breaks, I don't just fix and move on. I write a postmortem (5 lines, takes 2 min) capturing:
1. What happened (one sentence)
2. Root cause (the actual mechanism, not the symptom)
3. Fix applied
4. What would have caught it earlier (a check, a protocol, a different default)
5. What changes in claude-ops (new entry? expand stub? add to doctor.sh? amend CLAUDE.md?)

Without the postmortem, the lesson evaporates. Next session repeats the same failure.

## What to do when this triggers

```
1. Fix the immediate problem first (user time matters)
2. As soon as the fix is in:
   write 5-line postmortem in chat, propose adding to claude-ops
3. If user agrees → expand the relevant stub or add new entry
4. If user is busy → log it in this session's notes, propose at session end
5. NEVER let a notable failure pass without the writeup
```

## Format (the 5 lines)

```markdown
**Incident:** <one sentence what happened>
**Root cause:** <actual mechanism>
**Fix:** <what unblocked it>
**Would have caught earlier:** <specific check / protocol that would have prevented>
**Change in claude-ops:** <expand X stub / add to doctor.sh / amend CLAUDE.md>
```

## Concrete examples from real sessions

### ❌ Violation — YouTube n-challenge debug (2026-05-24)

I spent ~1h on yt-dlp ecosystem trying to fix downloads. When I finally pivoted, I just... moved on. No postmortem written. The lessons:
- "Detect upstream blocker after 2 same-category failures" (became `error-loop-detection.md`)
- "yt-dlp + IG cookies don't compose; cookies don't fix signature decoding"
- "Cloud provider IPs are blocked by youtube-transcript-api from datacenter"

ALL of these I had to re-derive 2 days later when writing this very repo. If I had spent 2 min on postmortem at the time, the lessons would have entered claude-ops 2 days earlier and could have helped intermediate sessions.

### ❌ Violation — Tech bot 75K token crash (2026-05-25)

Tech bot crashed because session accumulated 147 messages / 75K tokens, exceeding OpenAI quota + Groq TPM limit. We fixed by archiving the session file. Moved on.

Should have written:
> **Incident:** Tech bot stopped responding mid-flow. **Root cause:** session jsonl grew to 75K tokens, all 3 fallback models failed (quota / 413 / 400). **Fix:** archive session jsonl, fresh start. **Would have caught earlier:** session token counter visible to operator, alert at 50K. **Change in claude-ops:** `compaction-ritual.md` triggered at >50 messages or >40K context tokens; check session token usage in compute-ocv-1 doctor.

Without this writeup, the failure mode is invisible to next session.

### ✅ Correct behavior — supra-crm gitignore (2026-05-26, this session)

When `.env.example` was rejected by `.gitignore`:
- Fixed in 2 commits (force-add + .gitignore patch)
- Mentioned root cause in commit message explicitly
- Will add the lesson to `chunk-size-protocol.md` or a separate `gitignore-traps.md` if it repeats

Mini-postmortem, but it was there. The pattern was noted.

## Detection signals — when must I write a postmortem?

Trigger combinations (any 2 of these → required):

- ☐ Debug took longer than 30 minutes
- ☐ Tried 3+ different approaches before working
- ☐ Failure was a surprise (not predicted by current state)
- ☐ Failure was caused by my fabrication / extrapolation
- ☐ Failure pattern feels familiar from a previous session
- ☐ User had to step in with crucial context I missed

Any 2 of these → 5-line postmortem is mandatory.

## What this DOES NOT mean

- Not write a postmortem for every minor typo. Only NOTABLE failures.
- Not stop work for 30 min of analysis. 2 min, 5 lines.
- Not blame language. Postmortems are about the SYSTEM (what protocols / defaults / checks would prevent it), not "I should have been more careful."

## Enforcement loop

At the end of every work block (when transitioning to next task or closing session):

```
Did anything notable break in this block?
  → no: continue.
  → yes: write 5-line postmortem. propose claude-ops change.
         get user OK or note for later.
```

## Interaction with other protocols

- **`error-loop-detection.md`**: every escaped loop = postmortem-eligible event.
- **Rule #0 (no-fabrication)**: every caught fabrication = postmortem-eligible event.
- This is the protocol that FEEDS the other protocols. Without postmortems, claude-ops stops growing.
