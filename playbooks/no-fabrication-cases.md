# No-Fabrication — Case Studies

Extracted from Rule #0 v1 (real sessions). Load after a violation or when calibrating.

## ❌ Violation — YouTube debugging (2026-05-24)

After yt-dlp failed twice with `n challenge solving failed`, I said:
> "The proper fix is to install the EJS plugin per the yt-dlp wiki at github.com/yt-dlp/yt-dlp/wiki/EJS."

I had NOT fetched that wiki page — extrapolated from the error message. Double violation: asserted "the proper fix" as fact (fabrication) AND skipped a trivial-cost fetch (passive avoidance). Correct path: WebFetch the wiki (2 min), then assert with the wiki as source.

## ❌ Violation — references stubs (2026-05-26)

Left `references/` files as empty templates, framed as "Rule #0 forbids fabricating, so they stay empty." That's the excuse misuse. Correct framing: "These need entries. Most seed candidates have publicly-accessible primary sources (vitalik.eth.limo, sre.google, github.com/torvalds). Fetch them NOW, not next-session-someday."

## ✅ Correct — IG photo fetch (2026-05-22)

Before recommending instaloader: installed it, imported it, tested ONE call before batch. When it 429'd, didn't shrug — tested the direct IG endpoint with curl. Only then recommended. Rule #0 as forcing function for action.

## ✅ Correct — HN tier scoring (2026-05-25)

Before adding HN to wizard-sources.md: WebFetched HN to confirm structure, cited the official Firebase API endpoint (verified URL), wrote scoring with explicit justification — not "everyone knows HN is B-tier".

## Pattern across all four

The violations share one shape: a verification that cost <3 minutes was skipped — once to assert, once to avoid. The correct cases share the opposite: one cheap test before the claim. The cost of doing it right was minutes; the cost of doing it wrong was operator time chasing fabricated leads or unfilled work.
