# Chunk Size Protocol

**Status:** ✅ ACTIVE
**Priority:** medium
**Triggers:** About to generate >200 lines of code in a single output.

---

## What this rule says (to me, Claude)

Code generated in single shots >200 lines hides time-bombs that aren't apparent in review (per HN thread 48090029, 2026-05-25). The bigger the chunk, the more likely a fabricated import / wrong API / subtle bug is in there.

I split large work into chunks <200 lines. Between chunks, I VERIFY the chunk works (run test, lint, type-check, eyeball diff, or get user OK).

This is the most violated protocol in my history because shipping a single big script "feels efficient." It is not — it's deferred debugging that bites later.

## What to do when this triggers

```
1. Before writing: estimate output size.
   If >200 lines: split into chunks.
2. Plan chunks:
   - Each chunk = one coherent unit that can be VERIFIED independently
   - Order matters: foundations first, features built on top
3. Generate chunk 1.
4. VERIFY chunk 1 (run, test, lint, OR explicit user review).
5. Only proceed to chunk 2 if 1 verified.
6. Repeat.
7. If chunk N fails: fix chunk N before moving forward. Do not cascade fixes.
```

## Concrete examples from real sessions

### ❌ Violation — build-ambassadors.py v1 (2026-05-22)

Wrote 226 lines in single shot using instaloader. First run failed (instaloader rate-limited). Then realized the entire instaloader approach was wrong (graphql endpoint changed). Discarded most of it, rewrote with direct urllib endpoint.

If I had chunked:
- Chunk 1 (~30 lines): test ONE handle fetch with instaloader. → would have caught the rate-limit issue immediately.
- Chunk 2 (~40 lines): if chunk 1 OK, batch loop with rate limiting.
- Chunk 3 (~80 lines): if 2 OK, full CSV parsing + JSON output.
- Chunk 4: cleanup.

~70 lines wasted at most. Instead I wasted ~150.

### ❌ Violation — setup-pr scripts (multiple sessions)

I've shipped 300-400 line bash scripts that combine: repo clone + branch creation + file generation + commit + PR open. Each script runs as one shot.

When they fail, it's hard to know WHICH stage failed. The supra-crm one failed because of .gitignore wildcard — but the error message buried that. I had to inspect manually.

Better: scripts that are explicit about stages, with `echo "== stage N =="` between, and `set -e` to stop on first error. (Started doing this, still drift.)

### ❌ Violation — claude-ops bootstrap (THIS session, 2026-05-26)

Wrote a 287-line bash script for chunk 1 (foundational-brief + docs/* + base files). Got lucky it worked. Should have been ~3 sub-chunks.

The Rule #0 file itself (~152 lines) is on the line — was a single chunk. Acceptable as it's a single document, not multiple files.

### ✅ Correct behavior — claude-ops chunks A, B, C (this session)

Splitting protocol expansion into 3 SSH chunks (5 + 5 + 4 protocols). Each chunk is ~700 lines TOTAL but composed of 5 distinct files each ~150 lines. Each file is independently verifiable. Each chunk commits separately, so a failure in chunk B doesn't affect chunk A already in main.

This is the protocol applied correctly.

## Detection signals — am I about to violate this?

- ☐ My next output is going to be a single >200-line file
- ☐ I'm writing a bash script that combines >3 logical stages
- ☐ I'm generating multiple files in a single response without intermediate verification
- ☐ I haven't tested any part of what I'm about to ship
- ☐ I'm using "I'll fix bugs after" reasoning

Any → split. Plan chunks. Verify between.

## What this DOES NOT mean

- Not hard limit at 200 lines. Documentation files (this very file) can be longer if they're a single coherent unit reviewable as one.
- Not every code change. Trivial edits / single-function additions are fine in one shot.
- Not stop generating because line count rising. If the work is genuinely one coherent unit (e.g., this protocol file), continue.

The rule is about CODE that EXECUTES, and operations where failure is hard to localize. Markdown / docs / config files in single shot are usually fine.

## Enforcement loop

Before any non-trivial generation:

```
Estimate output size:
  ≤200 lines code / config / script that runs: just do it.
  >200 lines: SPLIT. plan chunks. verify each.
  >200 lines docs / single coherent doc: usually fine in one shot but check coherence.
```

## Interaction with other protocols

- **`error-loop-detection.md`**: big chunks often cause loops (debug the unknown 500-line script). Smaller chunks → faster pivot.
- **`survey-before-building.md`**: surveying often reveals existing code that means my chunk should be smaller (extend, not rewrite).
- **Rule #0**: bigger chunks correlate with more fabricated imports / wrong APIs. Smaller chunks let me verify each piece.
