# Grand Scheme First

**Status:** ✅ ACTIVE
**Priority:** medium
**Triggers:** About to design or implement a feature/component/endpoint without first sketching the big picture.

---

## What this rule says (to me, Claude)

Before any non-trivial feature implementation, I sketch the BIG PICTURE in chat:
- What's the user-visible outcome (one sentence)
- What layers does it touch (UI, API, DB, external services)
- Where does data flow (start → end)
- What's the smallest end-to-end version that works (the "tracer bullet")
- What gets cut for v1 (explicit scope reduction)

This sketch is RESEARCH mode output (see `mode-separation.md`). Operator confirms or adjusts. THEN I execute.

Skipping the grand scheme = building a beautiful feature that doesn't connect to anything (operator's brief #1, #3, #4).

## What to do when this triggers

```
1. Recognize: I'm about to write code for a "feature" / "component" / "endpoint" / "workflow"
2. STOP. Write the big picture in chat:
   - User outcome (1 sentence)
   - Layers touched (list)
   - Data flow (start → end, in arrows)
   - Smallest E2E ("tracer bullet"): what's the minimum that works end-to-end?
   - v1 scope cut: what we're NOT doing yet (and why)
3. Get operator OK on the sketch
4. EXECUTE the tracer bullet first (the smallest E2E)
5. Then layer features on top
```

## Format of the sketch

```markdown
**Feature:** <one-liner>
**User outcome:** <what they see / can do>

**Data flow:**
  User action → Frontend X → API Y → DB Z → response → user sees Q

**Layers touched:**
  - Frontend: <files / components>
  - API: <endpoints>
  - DB: <tables / migrations>
  - External: <services / integrations>

**Tracer bullet (smallest E2E):**
  <description of minimal version that proves the data path works>

**v1 scope cut:**
  - NOT doing: <feature A> (why: <reason>)
  - NOT doing: <feature B> (why: <reason>)

**v1 success criteria:**
  - <observable outcome>
```

## Concrete examples from real sessions

### ❌ Violation — extract-features.py (2026-05-22)

Went straight to "let me code the extractor" without sketching:
- What is the user outcome? (KNN that surfaces signals about reels)
- What's the smallest E2E? (1 reel → 1 features.json → 1 KNN query)
- What gets cut for v1? (engagement prediction needs labels, defer)

Result: built feature extractor in isolation, then realized later we don't have engagement labels, so the predictive part doesn't work. Could have caught this in 3 min of sketching.

### ❌ Violation — Path B initial spec (2026-05-22)

Wrote a 324-line spec for the bridge BEFORE sketching the user outcome:
- Who triggers this? (a writer in content-engine? a renderer in jarvis?)
- What's the minimal end-to-end? (one proposal becomes one rendered reel)
- What gets cut for v1? (image-chain, multi-format, auto-publish — all deferred)

Operator's "Carril A vs B" decision (path A first as foundation) was effectively the missing sketch. Should have produced it first.

### ✅ Correct behavior — workflow framework rollout (2026-05-26)

Before writing any state.md or Makefile, I sketched in chat:
- User outcome: "anyone (human or Claude) opens a repo and knows current state in 2 min"
- Layers: docs/ (state.md), root (Makefile), scripts/ (doctor.sh)
- Tracer bullet: apply pattern to content-engine first (gold standard), iterate
- v1 cut: no CI integration yet, no ADR formalization yet, no global enforcement

Operator confirmed sketch. Then I executed cleanly across 3 repos.

## Detection signals — should I sketch first?

- ☐ The work involves more than one file
- ☐ The work involves more than one layer (FE + BE, DB + API, etc.)
- ☐ The work involves a new feature visible to a user / operator
- ☐ I'd describe what I'm doing as "a system" rather than "an edit"
- ☐ I haven't said the words "tracer bullet" or "smallest E2E" yet

Any 2 → sketch first.

## What this DOES NOT mean

- Not sketch for trivial edits ("fix this typo", "rename this variable") — those don't need a sketch.
- Not block on operator sketch approval forever. 1-2 turn review is enough.
- Not write a 1000-line spec. The sketch is ~20 lines max. Specs come later if needed.

## Enforcement loop

Before any code work on what feels like a "feature":

```
Is this a single-file edit?
  → yes: just do it.
  → no: sketch first (≤20 lines in chat). get operator confirm. then execute.
```

## Interaction with other protocols

- **`mode-separation.md`**: sketching is RESEARCH mode. Coding is EXECUTE mode. Don't mix.
- **`survey-before-building.md`**: survey existing code FIRST, then sketch. Sketch references survey findings.
- **`functional-first.md`**: tracer bullet = functional-first incarnated. Smallest E2E that works > polished pieces that don't connect.
- **`layer-by-layer.md`**: the sketch reveals the layers; implementation goes layer-by-layer, not shotgun.
