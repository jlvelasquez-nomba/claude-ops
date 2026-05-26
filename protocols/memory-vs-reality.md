# Memory vs Reality

**Status:** ✅ ACTIVE
**Priority:** high (special case of Rule #0)
**Triggers:** I'm about to assume something is true based on what I remember (not what I just checked).

---

## What this rule says (to me, Claude)

My memory of a repo / deployment / conversation / library API is a STARTING HYPOTHESIS, never a fact. Before asserting or acting on memory:
- Verify against current reality (git log, grep, gh pr list, docs fetch, curl test, ls)
- If verification disagrees with memory → trust the verification, update memory, flag drift to user
- Never say "this is how X is" based on memory older than 5 minutes

## What to do when this triggers

```
1. NOTICE: am I about to assert/act based on memory?
   Common triggers: "based on what we set up", "the repo should have X",
                    "version Y of lib Z does W", "we decided X earlier"
2. VERIFY before acting:
   - Repo state → git log + ls + read state.md
   - Deployment → curl health endpoint
   - Conversation history → re-read recent messages
   - Library/API → fetch docs + grep source
3. If reality matches memory → proceed, mention "verified"
4. If reality differs → trust reality, update memory, FLAG drift to user
5. Never paper over the drift silently
```

## Concrete examples from real sessions

### ❌ Violation — Wizard "terminal-only" assumption (2026-05-21)

Memory said: *"Wizard is terminal-only; Slack/Telegram tokens not yet wired."*

I acted on this for ~3 messages designing how to send Wizard a prompt via CLI. Eventually saw Slack session ID `c0b2kjrp2na` in logs → realized memory was stale. Wizard had Slack wired up.

Should have, at the FIRST mention of Wizard's setup:
1. `docker exec openclaw-wizard env | grep SLACK` (10 seconds)
2. `docker logs openclaw-wizard --tail 20 | grep slack` (10 seconds)
3. THEN propose how to interact with Wizard

20 seconds of verification, saved 3 messages of wrong-track designing.

### ❌ Violation — Blueprint v2 spec from stale tech-audit (2026-05-22)

Memory + the `tech-audit.md` (dated May 14-21) said jarvis/video-starter was at a specific state. I designed a full Blueprint v2 spec based on that document.

Reality: jarvis had merged 11 more PRs since the audit, the actual Blueprint schema was at v1.2 with new fields (`render`, `asset_requests`) the audit didn't document.

Should have, BEFORE writing the spec:
1. `cd /opt/openclaw-stack/shared/repos/jarvis && git log --oneline -20`
2. `cat src/blueprint/types.ts`
3. `ls .claude/skills/reel-blueprint/examples/`

30 seconds of survey, would have saved the entire mis-aligned spec (~400 lines I had to throw away).

### ✅ Correct behavior — supra-crm survey (2026-05-26)

Before applying state.md/Makefile/doctor template to supra-crm, I:
1. `grep -rhoE 'import.meta.env.[A-Z_]+|process.env.[A-Z_]+'` to find ACTUAL env vars used
2. `cat package.json` for actual scripts and deps
3. `ls -la` root to spot deno.lock orphan
4. `git log --oneline -10` for recent commits

The .env.example I produced had 12 integrations matching ACTUAL code. Would have been wrong if I had used memory ("supra-crm probably uses Supabase + Notion + Stripe").

## Detection signals — am I about to violate this?

- ☐ I'm typing "the repo has X" without having ls'd in this session
- ☐ I'm typing "we decided X" without having grep'd the chat or docs/decisions.md
- ☐ I'm citing a version number / config value / file path from memory
- ☐ I'm acting on a memory of "the last time I worked on this"
- ☐ I'm proposing a fix based on a recalled API signature

When any → pause. Verify. Then act.

## What this DOES NOT mean

- Not refuse to use memory entirely. Memory is useful as STARTING hypothesis.
- Not verify everything. Trivial obvious facts (this is a TS file) don't need re-verification.
- Not slow to a crawl. Verification is fast for most things (one grep or one curl).

The rule is: verify before ASSERT-as-fact. Use memory as guess but label it ("I think... let me check").

## Enforcement loop

Every time my next sentence would be a factual claim about a repo, deployment, lib, or prior decision:

```
Was this verified in the last ~5 minutes of this session?
  → yes: proceed.
  → no: verify now. ONE command (grep / curl / cat / gh / git).
        If still asserting → cite the verification result.
        If can't verify quickly → label as guess (Rule #0).
```

## Interaction with other protocols

- **Rule #0 (no-fabrication)**: this is the memory-flavored special case. Same enforcement.
- **`survey-before-building.md`**: surveying = the verification step against memory of "what's in the repo".
- **`postmortem-ritual.md`**: every time memory caused real failure, write entry so the pattern stays codified.
