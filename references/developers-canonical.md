# Developers — canonical list

**Status:** 🟡 TEMPLATE · no canonical entries yet
**Per Rule #0:** every entry MUST have verified primary source link before promoting to canonical
**Per operator (2026-05-26):** "intentar tener una red buena, ni muy grande pero ni tan chica, de estos developers"

---

## Canonical entries

_(empty — each entry promoted from TODO list below only after verification)_

## TODO — candidate seed list

Names from operator brief #6 + obvious additions. Each requires verification before promotion.

| Candidate | Why relevant | Primary sources to verify |
|---|---|---|
| Linus Torvalds | code review discipline, git workflow, kernel maintainership | kernel.org, github.com/torvalds, LKML archive |
| Vitalik Buterin | EIPs as formal proposal process, long-form thinking | vitalik.eth.limo, eips.ethereum.org, github.com/vbuterin |
| Steve Wozniak | engineering simplicity, finishing things | woz.org, 'iWoz' book |
| Dan Abramov | React mental models, technical writing clarity | overreacted.io, github.com/gaearon |
| Rich Harris | Svelte design choices, framework critique | svelte.dev, github.com/Rich-Harris |
| Guillermo Rauch | DX, framework design (Next.js, Vercel) | rauchg.com, github.com/rauchg |
| DHH | Rails philosophy, conceptual compression | dhh.dk, github.com/dhh |
| Andrej Karpathy | ML pedagogy, building from scratch | karpathy.ai, github.com/karpathy, his YouTube |
| John Carmack | working speed, deep technical writing | Carmack .plan archive, his Twitter/X |
| Antirez (Salvatore Sanfilippo) | Redis design, antirez blog | antirez.com, github.com/antirez |
| Mitchell Hashimoto | small focused tools, terminal-first | mitchellh.com, HashiCorp blog |
| Cassidy Williams | dev advocacy, accessible explanations | cassidoo.co, github.com/cassidoo |
| Patrick McKenzie (patio11) | technical communication, software business | kalzumeus.com, his Twitter/X |
| Julia Evans (b0rk) | zines as docs, learning in public | jvns.ca, wizardzines.com |
| Simon Willison | datasette, AI tools blogging | simonwillison.net, github.com/simonw |

## Format for canonical entries (when verified)

```markdown
## <Full Name>

- **Personal site (verified):** <URL>
- **GitHub (verified):** <URL>
- **Verified social account:** <URL with link to verification — bluechecks have been gamed, prefer self-linked-from-personal-site>
- **Other primary sources:** <books with ISBN, papers with DOI, talks on official channels>
- **⚠️ Caveats:** <common misattributions, parts of internet that misquote them>
- **Topics of expertise (with source per claim):**
  - <topic 1> → <source where they discuss it>
  - <topic 2> → <source>

**Date verified:** YYYY-MM-DD
**Reviewed by operator:** ✅ / ⏳
```

## Verification workflow

1. Pick 1 candidate from TODO list
2. WebFetch each "Primary sources to verify" URL
3. If URL returns the dev's actual content: ✅, write entry
4. If URL is dead / wrong / fabricated: remove from TODO, do not promote
5. Submit entry to operator for review
6. On approval: move from TODO section to Canonical section
