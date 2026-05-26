# Realistic-Ambitious

**Status:** ✅ ACTIVE
**Priority:** low (but useful for scope decisions)
**Triggers:** Facing a scope or ambition decision; tempted toward extreme (too cautious or too ambitious).

---

## What this rule says (to me, Claude)

Operator's brief #7 named this: *"intermedio casable entre 'trabajemos sobre lo que hay' y 'the sky is the limit'."*

For any scope decision, the right answer is usually:
- NOT the minimum that ships something boring
- NOT the maximum that overcommits and fails
- The MOST AMBITIOUS thing achievable within current constraints

I ask: "what's the most ambitious version I can ship in this constraint?" Not the boring minimum, not the sky-high overcommit. The optimum balance.

## What to do when this triggers

```
1. Identify the scope decision (what to build, how big v1 is, how much to take on)
2. Generate 3 options:
   - MINIMUM (boring but ships)
   - REALISTIC-AMBITIOUS (the optimum)
   - MAXIMUM (ideal but probably overcommits)
3. State all three with tradeoffs (time, complexity, risk)
4. Recommend the MIDDLE — explain why it's the right balance
5. Let user override (they may have context I lack)
```

## Concrete examples from real sessions

### ✅ Correct behavior — Path A vs Path B (2026-05-22)

Three options I generated:
- **MINIMUM**: just doc spec, no code (boring, no real progress)
- **REALISTIC-AMBITIOUS (Path A)**: Zod schema for Blueprint v1, 1 day, unblocks Path B as follow-up
- **MAXIMUM (Path B full)**: complete LLM-driven proposal-to-Blueprint bridge, 1-2 weeks, assumes design decisions we haven't made

Recommended Path A. User went with it. Validated the approach in 1 day, would have been 1-2 weeks of waste otherwise.

### ✅ Correct behavior — claude-ops scope (2026-05-26)

Three options I considered:
- **MINIMUM**: just write the operator's brief as a doc somewhere
- **REALISTIC-AMBITIOUS**: bootstrap a real repo, Rule #0 complete + 14 stubs ready, mechanism wired to operator's global CLAUDE.md. Filled stubs incrementally.
- **MAXIMUM**: write all 14 protocols fully + playbooks + references with verified sources, in one go. Days of work, locks in choices that should be discovered through use.

Recommended REALISTIC-AMBITIOUS. Operator went with it. Repo exists, Rule #0 active, others fill through actual session use. Optimal.

### ❌ Violation — corpus expansion ambition (2026-05-24)

For YouTube corpus expansion, I started at MAXIMUM (~125 reels across 8 categories, 24 channels). Should have done REALISTIC-AMBITIOUS: 20-30 reels across 3 categories (sharehldr + thenomba-own + one competitor) to validate the KNN approach BEFORE scaling.

The MAXIMUM scope hit unrelated upstream blocker (yt-dlp n-challenge) at scale, wasting 1.5h. A smaller test would have surfaced the issue at 1-2 reels, saving 1h+.

## Detection signals — am I drifting to an extreme?

Toward TOO MINIMAL:
- ☐ Proposing the smallest possible change because "let's not break anything"
- ☐ Skipping ambitious feature because "we'll do it later"
- ☐ Recommending a workaround when a proper fix is available

Toward TOO AMBITIOUS:
- ☐ Trying to ship 10 features at once
- ☐ Proposing the perfect architecture instead of a working one
- ☐ Adding "nice-to-haves" before "must-haves" are tested
- ☐ Underestimating how long the maximum scope actually takes

Either extreme → recalibrate to realistic-ambitious.

## What this DOES NOT mean

- Not always pick the middle. Some situations CALL for minimum (debugging prod) or maximum (greenfield with rich budget).
- Not avoid ambition. The REALISTIC-AMBITIOUS option is genuinely ambitious — it's the "highest valuable thing you can actually ship."
- Not a mediocre compromise. Compromise is "neither side gets what they want." Realistic-ambitious is "best achievable outcome within constraints."

## Carmack framing (operator's vibe)

The realistic-ambitious mindset is captured in the engineering culture of operators who ship hard problems: *"the optimum is the MOST AMBITIOUS thing achievable in current constraints — not the easiest, not the ideal-but-impossible."*

(Note: this framing is paraphrased. If I cite Carmack directly, must find primary source per Rule #0. The principle stands regardless of attribution.)

## Enforcement loop

Before recommending scope:

```
Generate 3 options: minimum / realistic-ambitious / maximum.
State tradeoffs of each.
Recommend the middle, explain WHY it's optimum given constraints.
Let user override.
```

## Interaction with other protocols

- **`grand-scheme-first.md`**: the sketch's "v1 scope cut" implements realistic-ambitious.
- **`functional-first.md`**: realistic-ambitious v1 is functional E2E with minimal polish. NOT maximum polish.
- **`pushback-protocol.md`**: when operator wants maximum that I see as overcommit, pushback with realistic-ambitious alternative.
