# Mode Separation (Research vs Execute)

**Status:** ✅ ACTIVE
**Priority:** medium
**Triggers:** Work involves both "figure out what to do" (research / explore) and "do it" (execute / implement) in same flow.

---

## What this rule says (to me, Claude)

Research and execute are different modes. Mixing them in one flow causes:
- Code written before design is finalized (rework)
- Investigation aborted because "we have something running" (premature lock-in)
- Decisions buried inside implementation files instead of explicit ADRs

I declare mode explicitly at the start of a work block:

| Mode | What I do | What I do NOT do |
|---|---|---|
| **RESEARCH** | Read code, fetch docs, run experiments, summarize findings. Output: a writeup. | NO code commits. NO file edits in production paths. NO architecture decisions made. |
| **EXECUTE** | Implement against a clear decision. Commit, test, push. Output: shipped code. | NO research mid-flow. If question arises requiring research → pause execute, transition explicitly. |

## What to do when this triggers

```
1. At start of a work block, ask: "is this RESEARCH or EXECUTE?"
2. State mode explicitly in chat:
   "RESEARCH mode: investigating X. Output will be a writeup, no code committed."
   OR
   "EXECUTE mode: implementing decision X (per ADR/spec). Output will be PR."
3. If during RESEARCH I hit a decision point requiring user input → present findings + options, wait for decision.
4. If during EXECUTE I hit a question I can't answer → stop, state transition:
   "EXECUTE paused → RESEARCH: need to understand X before continuing. Will report back."
5. Never silently drift from RESEARCH to EXECUTE mid-flow.
```

## Concrete examples from real sessions

### ❌ Violation — Path B Spec drift (2026-05-22)

Started as: *"let me research the gap between content-engine and jarvis"* (RESEARCH mode).

Drifted to: *"here's the schema design"* (decision-making) → *"here are 400 lines of code"* (EXECUTE).

Problem: the schema was based on memory of the repos, not on actual current state. The 400 lines were thrown away when survey revealed jarvis was at v1.2 with extras.

What should have happened:
- RESEARCH mode: survey both repos, summarize current state, identify gap. Output: a writeup (the path-b-spec.md).
- WAIT for operator to approve scope (Path A vs B).
- EXECUTE mode: implement Path A as PR.

Mixing modes caused the 400-line write-then-discard cycle.

### ✅ Correct behavior — workflow framework rollout (2026-05-26)

I separated clearly:
1. RESEARCH: surveyed all 3 repos (content-engine, jarvis, supra-crm). Output: a comparison table.
2. PROPOSAL: state.md + Makefile + doctor templates designed. Output: file contents previewed.
3. DECISION: user picked option / order.
4. EXECUTE: setup-pr scripts for each repo, one PR per repo.

Three modes, three phases, clear transitions. Result: 3 PRs in 3 repos without rework.

### ✅ Correct behavior — claude-ops bootstrap (this session, 2026-05-26)

Mode declared explicitly: this is EXECUTE mode (Option 1 chosen from prior AskUserQuestion). Operating against the structure decided in the prior message. Each chunk is a tight execute block (5 protocols at a time).

If user mid-bootstrap had asked "should we also add anti-patterns/?" — that's a RESEARCH question, I would pause execute and discuss before continuing.

## Detection signals — am I mixing modes?

- ☐ I'm "investigating" but already 100 lines into writing code
- ☐ I'm "implementing" but I don't have a clear spec / ADR
- ☐ Mid-implementation I realize I need to fetch docs / run experiments
- ☐ Decisions are landing inside commit messages instead of docs/decisions.md
- ☐ User asks "what did we decide?" and I have to scroll back to derive it from code

Any → declare transition explicitly, OR pause and re-decide mode.

## What this DOES NOT mean

- Not bureaucratic mode-switching for trivial tasks. "Fix this typo" is execute, no mode declaration needed.
- Not stop being curious in execute mode. Curiosity is fine; commit-discarding ad-lib code is not.
- Not refuse to research mid-execute. Just declare the transition.

## Enforcement loop

At the start of any work block of >2 turns:

```
What mode is this?
  → RESEARCH: declare it. output = writeup, not code.
  → EXECUTE: declare it. commit small chunks, verify each.
  → MIXED (likely): split. research first, then decision, then execute.
```

During work, monitor for drift. If detected → transition explicitly.

## Interaction with other protocols

- **`grand-scheme-first.md`**: grand scheme is a RESEARCH output. Sketch it in research mode before executing features.
- **`survey-before-building.md`**: surveying is a research step. Required before execute, NOT during.
- **`chunk-size-protocol.md`**: execute mode commits in <200-line chunks with verification between. Research mode can produce longer writeups.
