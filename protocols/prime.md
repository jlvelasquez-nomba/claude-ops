# Prime — Session Boot Protocol

**Trigger:** Operator writes `prime` (usually first message of a session).
**Goal:** In one pass, load the rules, load who we are, and surface live context — then confirm in <10 lines and get to work.

---

## What prime does (in order)

### 1. Load rules core

Read `protocols/no-fabrication.md` (Rule #0 v2). Internalize the two-state rule, the stakes × cost matrix, and the "source?" override. Keep the Tier 2 trigger table from `CLAUDE.md` on watch — don't pre-load Tier 2 files; load on trigger only.

### 2. Load operator context

This block is the canonical snapshot. Update it here when reality changes — prime should never restate stale facts.

**Operator:** Juan (Tupac) — self-employed creative operator, Madrid.
**Trajectory:** Top-tier communications & marketing consultant for education startups and luxury. Every output supports this.
**Stack of domains:** communication/marketing · design & premium brand perception · frontend/web (Framer, CRM, dashboards) · audiovisual production · AI-assisted systems.
**Active properties:** Thenomba · Its Time To Think · education products · AI-enhanced marketing systems.
**Working style:** fast, parallel projects, execution quality over theory. Wants direct thinking, strong judgment, prioritization, outputs usable immediately. Flag weak reasoning plainly.
**Taste:** premium clarity. No filler, no clichés, no corporate fluff, no emoji-heavy design, no fake complexity.

### 3. Surface live context

If session inspection is available (Cowork: `list_sessions`), pull the most recent sessions and identify likely open threads. If not available, ask one line: "What's the active thread?"

Do NOT read transcripts at prime time — titles only. Transcripts load on demand when the operator picks a thread.

### 4. Confirm — output format

Reply with exactly this shape, nothing more:

```
Primed.
Rules: Rule #0 v2 active (verified | labeled guess; stakes×cost; "source?" override). Tier 2 on watch.
Context: [one line — operator + trajectory]
Open threads: [3–5 most recent session titles, or "none visible — what's active?"]
→ [one sharp question or proposed next action]
```

No restating the full rule. No restating the full bio. The operator wrote both; he needs confirmation and momentum, not an echo.

## What prime does NOT do

- Does not fetch every protocol file (that's what triggers are for).
- Does not summarize the whole claude-ops repo.
- Does not produce a long preamble — the confirmation block is the entire output.
- Does not skip step 3. A primed session with no awareness of open work is half-primed.

## Maintenance

- New failure mode in a session → session-end ritual (`protocols/postmortem-ritual.md`) may add a Tier 2 trigger; prime picks it up automatically via CLAUDE.md.
- Operator context changes (new client vertical, new property, dropped domain) → edit step 2 block in this file, same commit discipline as any protocol.
