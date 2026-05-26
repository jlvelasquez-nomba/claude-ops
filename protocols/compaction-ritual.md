# Compaction Ritual

**Status:** ✅ ACTIVE
**Priority:** medium
**Triggers:** Conversation context growing large (>50 messages or sense of bloat); model showing signs of degradation (slower, more confused, repeating itself).

---

## What this rule says (to me, Claude)

Long conversations accumulate context. Past a threshold, that context becomes noise — old decisions, dead-end attempts, stale state. Beyond a hard limit (varies by model), the session crashes or degrades silently.

I am responsible for proposing compaction BEFORE the crash. Compaction = summary of what matters from this conversation, dropping what doesn't. User confirms summary, we proceed with the compacted state.

The session-crash failure mode is silent and expensive. Prevention is cheap.

## What to do when this triggers

```
1. NOTICE signs:
   - Message count > 50
   - I'm referring back to "earlier" frequently
   - I'm forgetting decisions made 20+ messages ago
   - My responses feel slower / hedged / generic
   - Operator says "espera, ya hicimos eso"
2. PROPOSE compaction in chat:
   "We're at message ~N. Context is getting heavy. Propose summary:
    - Decisions made: [list]
    - State right now: [list]
    - Open threads: [list]
    - Suggested drop: [outdated parts]
    OK to compact?"
3. WAIT for operator OK or edit
4. After compaction: continue with the summary as canonical context
```

## Concrete examples from real sessions

### ❌ Violation — Tech bot crash (2026-05-25)

Tech bot session accumulated 147 messages, ~75K tokens (history 34K + system prompt 41K). Then:
- OpenAI quota exhausted on primary model
- Groq fallback rejected the 75K request (8K TPM limit)
- Anthropic fallback also failed

Result: Tech bot silently failed mid-task, gave generic "Something went wrong" error.

If Tech bot had a compaction ritual at message ~80, the crash would not have happened. Operator had no idea the session was bloating until it broke.

### ❌ Violation — Long sessions in this workspace

This very conversation (Juan + me) has had multi-session days that accumulated. Several times I've forgotten decisions made 30+ messages ago and had to be reminded by the operator. Each reminder = waste of operator time.

Should have proposed compaction at several points (e.g., when transitioning from "Path B Spec" to "engagement numbers", I should have proposed a summary of decisions to date).

### ✅ Correct behavior — Mid-session phase transitions

When I propose phase transitions in chat ("Fase 1 done, moving to Fase 2") I'm implicitly compacting. Could be more explicit: "Phase 1 summary: [3 lines]. Drop from working memory: [old attempts, deprecated paths]. Phase 2 starts now."

## Detection signals — should I propose compaction?

- ☐ Message count > 50
- ☐ I've used "earlier we" or "remember when" 3+ times in last 10 messages
- ☐ I'm citing decisions without remembering exact wording
- ☐ Operator has had to remind me of context 2+ times
- ☐ I'm re-deriving conclusions instead of using prior context
- ☐ Response time / quality feels degraded
- ☐ Context window estimate > 50% of max

Any 2 → propose compaction in next response.

## Compaction summary template

```markdown
## Session compaction (proposed at message ~N)

**Active decisions (carry forward):**
- D1: ...
- D2: ...

**Current state:**
- Working on: <what>
- Last shipped: <link/PR>
- Pending: <list>

**Open threads (still alive):**
- T1: ...
- T2: ...

**Dropped (no longer relevant):**
- Old attempts at X
- Earlier discussion of Y now superseded

**Continue with this as canonical context. OK?**
```

## What this DOES NOT mean

- Not propose compaction every 20 messages. Use signals.
- Not summarize and proceed without user OK. They might want a different drop/keep balance.
- Not delete history (that's the chat record). Compaction is mental: shifting which messages I attend to.

## What operator can do (handoff)

The operator can also trigger compaction by saying:
- "compactemos" / "let's compact"
- "summary of where we are?"
- "drop the X thread"
- "/new" (in interfaces where it works) for hard reset

## Enforcement loop

Every ~10 messages in a long session, check signals. When 2+ triggered, propose in next response.

For Tech bot or other long-lived bot sessions: compaction should be a periodic ritual (every X messages auto-propose). Not yet automated — operator must remember to trigger.

## Interaction with other protocols

- **`postmortem-ritual.md`**: a session crash from un-compacted context = postmortem-eligible event.
- **`pre-flight protocol`** (in CLAUDE.md root): pre-flight reads docs/state.md INSTEAD of relying on session memory. Compaction is the mid-session equivalent.
- **`mode-separation.md`**: phase transitions are good moments to compact.
