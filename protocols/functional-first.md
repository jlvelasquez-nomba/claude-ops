# Functional First (over pretty)

**Status:** ✅ ACTIVE
**Priority:** medium
**Triggers:** Building user-facing UI / styling / animations / interactions while backend / API / data layer isn't proven working end-to-end yet.

---

## What this rule says (to me, Claude)

A button that LOOKS good but doesn't trigger anything is WORSE than no button. It sets wrong expectations. Styling and polish are the LAST step, after the data path works end-to-end.

Order of priority:
1. Does the happy path work E2E? (data flows from input to output, button click → backend → DB → response → user sees result)
2. Does it handle the obvious unhappy paths? (empty state, error state, loading state)
3. Now make it pretty.

If 1 isn't working, do not touch 3.

Operator's brief #4: *"se rompe, los spacings y los paddings no respetan nada... ni mockup chulo ni modelo funcional."* The shotgun anti-pattern.

## What to do when this triggers

```
1. Identify the user-visible feature
2. Strip to its minimum interactive surface (one form, one button, one rendered output)
3. Build that minimum WITH real backend behind it
   - Click button → real API call → real response → real render
4. VERIFY the happy path works (try it, screenshot it, get user OK)
5. Add error states (network fail, validation fail) — verify each
6. Add loading states
7. NOW polish: typography, spacing, color, animation
8. NEVER step 7 before step 4 is proven
```

## Concrete examples from real sessions

### ❌ Violation — hypothetical SaaS booking shotgun (operator brief #4)

The brief explicitly describes this anti-pattern: build pretty UI, none of it works, can't fix because the polish and structure compete for attention. Tokens, time, money wasted.

Functional-first would have been:
- Ugly button labeled "Book Now" → makes real API call → real booking in DB → ugly success message
- Then ugly form with date picker
- Then ugly list of bookings
- THEN polish all of it

### ✅ Correct behavior — claude-ops bootstrap (2026-05-26)

When building this repo, I focused on functional first:
- Rule #0 written as a USABLE protocol (real triggers, real examples, real enforcement loop). Not "Rule #0 nicely formatted with branded headers".
- Protocol stubs are functional skeletons (title + status + triggers + outline). Not "stubs with nice diagrams and animations".

Polish (table-of-contents at repo root, diagrams of how protocols interrelate, navigation aids) can come later. The CORE function (protocols I can load and act on) works now.

### ❌ Violation tendency — Markdown formatting in chat

I have a tendency to add tables / emojis / headers to chat responses BEFORE confirming the substance is right. Sometimes the operator wants to validate the approach first, and the pretty formatting just delays the actual review.

Should: state substance plainly first, format only if clarity demands it.

## Detection signals — am I about to violate this?

- ☐ I'm working on styling / animation / typography
- ☐ The underlying feature has not been tested end-to-end yet
- ☐ I'm adding "nice-to-have" UI niceties before "must-have" data flow works
- ☐ I haven't verified ONE happy-path interaction works
- ☐ I'm tempted to commit "WIP, will wire backend later"

Any → STOP polishing. Confirm functionality first.

## What this DOES NOT mean

- Not "ugly forever". Polish IS part of the work. Just sequence it correctly.
- Not "no design thinking allowed until backend works". Sketching UX, picking colors, mocking screens — all fine in RESEARCH mode. Just don't COMMIT styled-but-non-functional code as if it's done.
- Not "functional means ugly". A functional thing CAN be presentable. The point is not to add visual polish that masks broken behavior.

## A useful question to ask myself

> "If a user clicked this button right now, what would happen?"

If the answer is "I don't know" or "nothing" or "it would error" → I'm not in functional-first mode. Pause polish, fix the click action.

## Enforcement loop

Before any visual polish work:

```
Is the underlying happy path proven working E2E?
  → yes: polish away.
  → no: fix the data path first. polish is the LAST step.
```

## Interaction with other protocols

- **`layer-by-layer.md`**: layer-by-layer = order of build (bottom-up). Functional-first = within each layer, working > pretty.
- **`grand-scheme-first.md`**: the sketch's "tracer bullet" is functional-first incarnated.
- **`pushback-protocol.md`**: when operator asks for polish on a broken feature, pushback respectfully: "the button looks great but it doesn't actually book anything yet. should we wire the backend first, or do you want the visual mockup for an external presentation?"
