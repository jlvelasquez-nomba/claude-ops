# Developers — canonical list

**Status:** 🟢 ACTIVE · 4 canonical · 11 TODO
**Per Rule #0 (active interpretation):** entries verified via WebFetch on date noted. Goal: grow canonical list session by session, NOT keep empty.

---

## Canonical entries

### Vitalik Buterin

- **Personal site (verified):** https://vitalik.eth.limo — header identifies as "Vitalik Buterin's website" (accessed 2026-05-26)
- **Topics covered (verified from site categories):** Blockchains, Cryptography, Economics, Fun, General, Gitcoin, Math, Philosophy, Translations
- **Recent verified posts (sample, accessed 2026-05-26):**
  - "A shallow dive into formal verification" — 2026-05-18
  - "My self-sovereign / local / private / secure LLM setup, April 2026" — 2026-04-02
  - "Balance of power" — 2025-12-30
- **Authoritative on:** Ethereum protocol design, blockchain economics, cryptographic constructions (zk, etc.), governance / quadratic mechanisms
- **⚠️ Caveats:**
  - Twitter/X account NOT verified at this fetch — need separate verification before citing his social posts
  - Many "Vitalik quotes" floating online are translations or paraphrases. Always link to his original blog post.
- **Next verification step (to extend this entry):**
  - WebFetch a specific post (e.g., "Balance of power") for direct quote with paragraph anchor
  - Verify his X handle via cross-link from vitalik.eth.limo
- **Date verified:** 2026-05-26 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Julia Evans (b0rk)

- **Personal site (verified):** https://jvns.ca — header reads "Julia Evans" + intro "Hey! I'm Julia. Welcome to my blog." (accessed 2026-05-26)
- **Zines venture (verified):** https://wizardzines.com — linked from jvns.ca, "I publish computer zines at Wizard Zines"
- **Topics covered (verified from site sections):** debugging, computer networking (DNS, TCP), Linux, Git, CSS, web dev
- **Recent verified posts (sample, accessed 2026-05-26):**
  - "Moving away from Tailwind, and learning to structure my CSS" — 2026-05-15 (https://jvns.ca/blog/2026/05/15/moving-away-from-tailwind--and-learning-to-structure-my-css-/)
  - "Links to CSS colour palettes" — 2026-05-04 (https://jvns.ca/blog/2026/05/04/css-colour-palettes/)
  - "Testing Vue components in the browser" — 2026-05-02 (https://jvns.ca/blog/2026/05/02/testing-vue-components-in-the-browser/)
- **Authoritative on:** debugging methodology, Linux internals (strace, perf), networking fundamentals, technical writing for explanation
- **Visible pattern (verified from her structure):** writing accessible technical explanations for hard topics; using zines as a distribution format for compressed knowledge
- **⚠️ Caveats:** none flagged from fetch; her content is unambiguously hers
- **Next verification step:** fetch her zine catalog at wizardzines.com for specific titles + extract one explicit philosophy quote (e.g., from "A debugging manifesto")
- **Date verified:** 2026-05-26 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Simon Willison

- **Personal site (verified):** https://simonwillison.net — "Simon Willison's Weblog" in header (accessed 2026-05-26)
- **Adjacent verified property:** https://til.simonwillison.net — his "Today I Learned" repo, linked from main blog
- **Topics covered (verified from site tags):** Datasette (1,499+ tagged posts), LLMs, AI tooling, Python, open-source dev
- **Recent verified posts (sample, accessed 2026-05-26):**
  - "Notes on Pope Leo XIV's encyclical on AI" — 2026-05-25 (/2026/May/25/encyclical-on-ai/)
  - "Datasette Agent" — 2026-05-21 (/2026/May/21/datasette-agent/)
  - "Gemini 3.5 Flash: more expensive, but Google plan to use it for everything" — 2026-05-19 (/2026/May/19/gemini-35-flash/)
- **Authoritative on:** Datasette ecosystem, LLM tooling + evaluation, open-source plugin architecture
- **Visible patterns (verified from site structure):**
  - TIL format (Today-I-Learned notes as first-class artifacts)
  - Detailed release annotations on his projects (datasette 1.0a30, llm-gemini 0.32)
  - Plugin-first design across his tools (datasette-agent, datasette-llm, llm-gemini)
- **⚠️ Caveats:** none from fetch; voice + topics consistent with his known work
- **Next verification step:** fetch one specific post for a verifiable position quote, e.g., his stance on LLM eval methodology
- **Date verified:** 2026-05-26 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Mitchell Hashimoto

- **Personal site (verified):** https://mitchellh.com — bio confirms "developer living in Los Angeles, CA. I previously co-founded HashiCorp." (accessed 2026-05-26)
- **Current work (verified):** Ghostty terminal emulator
- **HashiCorp tools (verified from bio listing):** Vagrant, Terraform, Consul, Vault, Nomad, Waypoint
- **Topics covered (verified from bio):** infrastructure / DevOps tools, terminal emulation, aviation (he's a private pilot)
- **Authoritative on:** infrastructure-as-code (founder of the modern category with Terraform), CLI / terminal tooling, framework design at OSS scale
- **⚠️ Caveats:**
  - Homepage fetch did NOT return specific recent posts or his explicit writing philosophy (those live at /writing — not fetched yet)
  - Quotes about "small focused tools" or his design philosophy are widely paraphrased online; verify against /writing before citing specific positions
- **Next verification step:**
  - WebFetch https://mitchellh.com/writing (or whatever the writing index URL is)
  - Find one post explicitly stating a principle, extract verified quote with URL
- **Date verified:** 2026-05-26 (Claude session, WebFetch — partial)
- **Reviewed by operator:** ⏳

## TODO — candidates pending verification

Each row = active verification work to do, NOT permanently empty.

| Candidate | Why relevant | Next verification step | Status |
|---|---|---|---|
| Linus Torvalds | code review discipline, git workflow, kernel maintainership | WebFetch github.com/torvalds + one verified LKML thread quote | TODO |
| Steve Wozniak | engineering simplicity, finishing things | Verify woz.org alive; check Internet Archive for backup if needed | TODO |
| Dan Abramov | React mental models, technical writing clarity | WebFetch overreacted.io | TODO |
| Rich Harris | Svelte design choices, framework critique | WebFetch svelte.dev/team + recent Rich blog if any | TODO |
| Guillermo Rauch | DX, framework design (Next.js, Vercel) | WebFetch rauchg.com | TODO |
| DHH (David Heinemeier Hansson) | Rails philosophy, conceptual compression | WebFetch dhh.dk | TODO |
| Andrej Karpathy | ML pedagogy, building from scratch | WebFetch karpathy.ai | TODO |
| John Carmack | working speed, deep technical writing | Find Carmack's verified X account + .plan archive URL | TODO |
| Antirez (Salvatore Sanfilippo) | Redis design, antirez blog | WebFetch antirez.com | TODO |
| Cassidy Williams | dev advocacy, accessible explanations | WebFetch cassidoo.co | TODO |
| Patrick McKenzie (patio11) | technical communication, software business | WebFetch kalzumeus.com | TODO |

## Format for canonical entries

(See the entries above as worked examples.)

```markdown
### <Full Name>

- **Personal site (verified):** <URL> — what identifies it (accessed YYYY-MM-DD)
- **Topics covered (verified from <site source>):** ...
- **Recent verified posts:** ... (with URLs)
- **Authoritative on:** ...
- **Visible patterns (verified):** ...
- **⚠️ Caveats:** ...
- **Next verification step:** ...
- **Date verified:** YYYY-MM-DD by Claude session, WebFetch
- **Reviewed by operator:** ⏳ / ✅
```

## Verification workflow (active)

1. Pick 1 candidate from TODO list
2. WebFetch each "Next verification step" URL
3. If URL returns the dev's actual content: ✅, write entry following format
4. If URL is dead / wrong / fabricated: note explicitly in the TODO row what failed
5. Submit to operator for ratification
6. On approval: row moves from TODO to Canonical
