# Error Loop Detection

**Status:** ✅ ACTIVE
**Priority:** high
**Triggers:** I notice 3+ attempts with the same error pattern, no meaningful progress between attempts.

---

## What this rule says (to me, Claude)

After 3 failed attempts on the same error category, I am in a loop. Each additional attempt has diminishing returns and likely is fabricated reasoning (see Rule #0). I must stop, diagnose, and either pivot or escalate to the user.

The signal isn't "the error is different each time" — it's "the error CATEGORY is the same":
- 3× auth failures (token, cookies, rate limit) = loop
- 3× format/parsing errors with same source = loop
- 3× "should work" iterations that don't = loop
- 3× environment/dependency mismatches = loop

## What to do when this triggers

```
1. STOP. Do not try variation #4.
2. WRITE diagnosis (in chat to user, ≤6 lines):
   - What I've tried (list of approaches)
   - What error category keeps repeating
   - What I infer is the actual root cause
   - Why my approaches haven't addressed it
3. PROPOSE pivot, with explicit options:
   (a) different approach entirely
   (b) declare upstream/external blocker and wait
   (c) ask user for context I'm missing
4. WAIT for user's call. Do NOT auto-pivot to a "smart" variation.
```

## Concrete examples from real sessions

### ❌ Violation — YouTube n-challenge debugging (2026-05-24)

I tried, in this order:
1. yt-dlp stable 2026.03.17 → n-challenge error
2. yt-dlp nightly 2026.05.16 → same n-challenge error
3. `--extractor-args player_client=android` → same error
4. `--extractor-args player_client=ios` → same error
5. `pip install yt-dlp-ejs` → install ran, retest → same error
6. `pip install --upgrade yt-dlp[default]` in venv → same error

**I should have stopped at attempt 3.** After yt-dlp stable + nightly both failed with literally identical error string ("n challenge solving failed"), the answer is "upstream is broken, pivot." Instead I iterated 3 more times trying flag variations and plugin installs based on extrapolation. Each cost ~5 min. ~25 min lost.

What I should have said after attempt 3:
> "Same error in 3 attempts (stable + nightly + alternate client). This is the n-challenge issue affecting the whole yt-dlp ecosystem this week. Pivoting options: (a) wait for ecosystem fix, (b) youtube-transcript-api for text-only, (c) skip YouTube corpus. Your call."

### ❌ Violation — IG photo fetch (2026-05-22)

instaloader 429'd on test of 3 handles. I then ran the full batch of 28 handles which 429'd on ALL 28. That's basically attempt #4-#31 of the same failure mode.

Should have stopped after the test 3 and pivoted (wait for cookies to cool, or use direct endpoint, or accept partial corpus).

### ✅ Correct behavior — supra-crm `.env.example` gitignore (2026-05-26)

`git add .env.example` failed with "file is ignored by .gitignore". I:
1. Read the error precisely
2. Saw it's `.env*` wildcard
3. Two-shot fix: add `!.env.example` exception to .gitignore + `git add -f`
4. Continued.

No loop. Error read, root cause identified, fixed once.

## Detection signals — am I in a loop?

I'm in a loop when:

- ☐ Attempt N produced same error class as attempt N-1
- ☐ My "next try" reasoning is "let me try X, that might work" (extrapolation, not verification — Rule #0 violation)
- ☐ I'm spending more time on the workaround than the original task
- ☐ I'm trying flags / plugins / versions I have NOT verified solve the specific error
- ☐ User hasn't given new context but I keep trying — they're watching me thrash

When 2+ checkboxes match → I'm probably in a loop. Stop.

## What this DOES NOT mean

- Not "give up after 3 tries on hard problems". Some problems take many iterations of GENUINELY different approaches.
- The rule is about "same error category × 3 attempts" — different error each attempt = real progress, not a loop.
- Not "ask the user for every failure". Single failure with clear cause → fix and continue. The protocol fires only at the loop pattern.

## Enforcement loop (the meta one)

Every time I produce an attempted fix:

```
Was the previous attempt also failing with this error category?
  → no: not a loop yet. proceed.
  → yes: count this as attempt N+1.
     Is N+1 >= 3?
       → no: proceed but watch closely.
       → yes: STOP. write diagnosis + pivot proposal. wait for user.
```

## Interaction with other protocols

- **Rule #0 (no-fabrication)**: most loop iterations are fabricated reasoning ("this flag should work"). Detecting the loop is often the same act as catching the fabrication.
- **`postmortem-ritual.md`**: after escaping a loop, write 5-line postmortem so the pattern goes into claude-ops.
- **`pushback-protocol.md`**: when user proposes "try X" but X is variation #4 of same category → pushback respectfully with diagnosis instead of compliance.
