# Pro Dev Reference Patterns

**Status:** 🟡 TEMPLATE · entries pending Rule #0 source verification
**Per Rule #0:** NO entry below is written until I have a verified primary source link

---

## Why this is empty (and that's correct, not incomplete)

Rule #0 says: I do not write patterns "used by X dev" without their primary source. Most "famous dev quotes" on the internet are paraphrased or misattributed. Adding entries here without verification would be the worst kind of failure for this repo.

The CORRECT path: each entry gets added in a dedicated session where I (Claude) use WebFetch to verify the source, then write the entry. Operator reviews. Entry lands.

## TODO list (candidates from operator brief #6 + obvious additions)

| Candidate | Pattern category | Verification needed |
|---|---|---|
| Linus Torvalds | code review discipline, small commits, kernel maintainership | LKML thread + signed-off-by convention docs (lkml.org / kernel.org) |
| Vitalik Buterin | long-form deep thinking, EIPs as formal proposal | vitalik.eth.limo + eips.ethereum.org |
| Steve Wozniak | finish-what-you-start, simplicity | 'iWoz' book (ISBN 9780393330434) |
| Anthropic team | careful release, RSP, alignment-first | anthropic.com/news + responsible-scaling-policy.pdf |
| OpenAI team | rapid iteration with eval benchmarks | openai.com/research + github.com/openai/evals |
| Tesla/SpaceX | first principles, 'best part is no part' | Musk biographies (Vance, Isaacson) — quote with page citation |
| Google SRE | error budgets, postmortems, blast radius | sre.google book (free online, with chapter citations) |
| John Carmack | working-fast, deep technical empathy | Carmack's .plan archive + Lex Fridman interview transcripts |
| Mitchell Hashimoto | small focused tools, terminal-first | mitchellh.com + HashiCorp engineering blog |
| Julia Evans (b0rk) | learning in public, zines as docs | jvns.ca + her zines |

## Format for completed entries (template)

```markdown
## <Dev/Org Name>

**Verified primary sources:**
- <link 1, exact URL with date accessed>
- <link 2>
- <link 3 if relevant>

**Pattern (with verified quote):**
> "<exact quote with link to exact paragraph or timestamp>"
> — <Name>, <source title>, <date>

**My application — WHEN I should invoke this pattern:**
WHEN: <trigger>
THEN: <action>

**Anti-pattern this prevents:**
<what failure mode it stops>

**Date entry added:** <YYYY-MM-DD by Claude session>
**Date last verified:** <YYYY-MM-DD>
```

## Verification workflow per candidate

1. WebFetch the candidate's primary source URL
2. If the URL returns content: extract the verified pattern with quote
3. If the URL doesn't return content (auth-walled, dead, fabricated by me): mark TODO permanently, do NOT extrapolate
4. Write entry following template
5. Operator review
6. Commit

## Rule #0 enforcement reminder

If I'm tempted to write "Linus Torvalds famously said about small commits..." without a link to the specific email or commit message where he said it — I am violating Rule #0. The pattern still goes UNWRITTEN until I have the source.

Better empty than wrong.
