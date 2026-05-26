# Pro Dev Reference Patterns

**Status:** 🟡 STUB · awaiting verified primary sources for each entry
**Per Rule #0**: every pattern below MUST have a primary source link before being adopted

---

## Patterns to source (TODO)

Operator brief #6 named these as candidates. For each, I need to find verified primary source(s) and extract the actual pattern (no paraphrasing):

| Dev / Company | Pattern candidate | Primary source needed |
|---|---|---|
| Linus Torvalds | code review brutality, small focused commits | LKML thread + signed-off-by convention docs |
| Vitalik Buterin | long-form deep thinking before action, EIPs as formal proposal | vitalik.eth.limo posts + EIP process page |
| Steve Wozniak | finish what you start, simplicity over complexity | 'iWoz' book ISBN 9780393330434 |
| Anthropic | careful release with safety review | anthropic.com blog + responsible scaling policy |
| OpenAI | rapid iteration with measurable benchmarks | openai.com cookbook + eval frameworks |
| Tesla/SpaceX (Musk-led) | 'best part is no part', first principles | Musk biographies + Tim Dodd 5-step process video (sourced) |
| Google SRE | error budgets, postmortems | sre.google book (free online) |

## Format for completed entries (template)

```markdown
## <Dev Name>

**Verified primary sources:**
- <link 1>
- <link 2>

**Pattern (exact phrasing from source):**
> "<quote with link to exact paragraph>"

**My application (when I should invoke this pattern):**
<algorithmic: WHEN X THEN Y>

**Anti-pattern this prevents:**
<what failure mode it stops>
```

## Rule #0 enforcement here

No entry gets written without:
1. Primary source link (the dev's words, not paraphrased)
2. Quote with attribution to exact source location
3. Operator review (Juan can call "source?" on any entry)

If I can't find a primary source for an alleged pattern → that pattern doesn't go in this file.
