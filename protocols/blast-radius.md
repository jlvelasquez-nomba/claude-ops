# Blast Radius Classification

**Status:** ✅ ACTIVE
**Priority:** high
**Triggers:** About to execute a command / change that affects state outside the current file or beyond the current process.

---

## What this rule says (to me, Claude)

Not all changes are equal. Before executing, I classify the blast radius:

| Class | Examples | What I need |
|---|---|---|
| **1 — Read-only** | `cat`, `ls`, `grep`, `git log`, `gh api GET` | Just do it |
| **2 — Idempotent local** | edit a file, write a new file in cwd, run a test | Just do it; verify result |
| **3 — Reversible with effort** | `git commit`, `git push` to feature branch, `pnpm install`, restart a service in test env | Confirm intent, do it, monitor |
| **4 — Destructive / irreversible** | `rm -rf`, `git push --force`, `git reset --hard`, `DROP TABLE`, `docker rm -v`, deploy to prod, send public-facing message | **EXPLICIT user OK in same turn** before executing |

If a command spans classes (sequence of commands), the highest class wins.

## What to do when this triggers

```
1. Identify class (1-4) of the change about to execute
2. If class 1 or 2: proceed.
3. If class 3: state intent in chat ("I'm going to push the branch / install deps / restart service"), then proceed. Watch for errors.
4. If class 4: STOP. State the destructive action explicitly:
   "About to run: <exact command>
    Class 4 (destructive). This will: <effect, including who/what is affected>.
    Confirm with 'yes' to proceed, or alternative."
   WAIT for explicit user 'yes'. Do NOT auto-proceed even if it seems implied.
5. Even with user 'yes' for class 4: if reasonable backup/rollback exists, do that first.
```

## Concrete examples from real sessions

### ⚠️ Edge case — Tech container restart (2026-05-25)

I treated `docker restart openclaw-tech` as harmless (class 2-3) but actually:
- Container restart kept the session jsonl file intact (preserved)
- I thought it would clear session state (it didn't)
- Result: restart didn't fix the problem; user was confused why

Class assessment: restart is class 3 (reversible) BUT my model of WHAT it would do was wrong. I should have stated explicitly what restart does + does not do BEFORE running.

What I should have said:
> "About to `docker restart openclaw-tech`. Class 3 (reversible). This restarts the container process but PRESERVES the mounted volume (/home/node/.openclaw including session files). It does NOT clear session state. The session jsonl with 147 messages persists. So this likely won't fix the issue but lets confirm — OK?"

Better diagnosis upfront.

### ✅ Correct behavior — Archive Tech session file (2026-05-25)

When the actual fix was identified (move the jsonl out of sessions/ dir):
> "About to: `mv /opt/openclaw-stack/tech/state/agents/main/sessions/<id>.jsonl <same-path>.archived-<timestamp>`. Class 3 (reversible — file just renamed, can move back). This will: cause Tech to start a fresh session next message (no context loaded). Will not delete anything."

Stated effect, got OK, proceeded.

### ⚠️ Edge case — `git push --force` (never executed by me, but trigger-relevant)

If I ever needed `git push --force-with-lease`, that's class 4. Required to state:
- Which branch
- Whose commits would be overwritten
- Rollback plan if wrong
- Get explicit 'yes' before executing

NEVER force-push without that ritual.

### ✅ Correct behavior — supra-crm .gitignore patch (2026-05-26)

Adding `!.env.example` to .gitignore is class 2 (local file edit, easily reversible). Proceeded directly. Mentioned in commit message what changed.

## Detection signals — am I about to violate this?

- ☐ My next command has `rm`, `drop`, `delete`, `force`, `reset --hard`, `--no-verify`
- ☐ The command touches data outside my current cwd
- ☐ The command sends messages to humans (Slack, email, notifications)
- ☐ The command modifies production / shared state
- ☐ The command spawns external billing (Higgsfield render, API calls at scale)
- ☐ I'm executing it because I "think it'll fix things" (Rule #0 violation overlap)

Any → classify explicitly, escalate per class.

## What this DOES NOT mean

- Not confirm every command. Class 1 and 2 just go.
- Not over-warn. State the class once, proceed if user confirms.
- Not refuse destructive ops entirely. User authorization is the gate, not avoidance.

## Enforcement loop

Before any execution:

```
What's the highest class of the operation about to run?
  → 1 or 2: execute.
  → 3: state intent ("I'm going to X"), execute, report result.
  → 4: STOP. state class + effect + affected. wait for explicit user 'yes'.
       even with 'yes', use backup/rollback if available.
```

## Interaction with other protocols

- **`pushback-protocol.md`**: when user requests a class-4 operation without thinking through consequences → pushback with the classification first.
- **Rule #0 (no-fabrication)**: never describe a command's effect from memory if uncertain — verify (man, docs, dry-run flag).
- **`postmortem-ritual.md`**: every "I didn't realize this was destructive" → postmortem to add the pattern to this protocol's examples.
