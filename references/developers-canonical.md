# Developers — canonical list

**Status:** 🟢 ACTIVE · 14 canonical · 1 partial-verification · 0 TODO
**Per Rule #0 (active interpretation):** entries verified via WebFetch on date noted. Partial-verification entries (URL identified but fetch blocked) are honest about what failed and what to retry next session.

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

### Linus Torvalds

- **Canonical venue (verified):** https://github.com/torvalds — profile shows "Linus Torvalds" account, Portland OR, affiliated with Linux Foundation, 305k followers (accessed 2026-05-27)
- **Pinned repos (verified):** `linux` (Linux kernel source tree, 235k stars), plus personal projects: `GuitarPedal` ("Linus learns analog circuits"), `AudioNoise`, `uemacs`
- **Authoritative on:** Linux kernel design, Git internals (he wrote it), maintainer culture / code review discipline, OS-level system programming, long-term project leadership at scale
- **Visible patterns (verified from his repo curation):** uses GitHub for kernel mirror but does NOT take PRs there (kernel work happens on LKML); hobby projects show same hands-on building habit he applies to kernel work
- **⚠️ Caveats:**
  - GitHub is a MIRROR of kernel work, not the source — actual kernel discussions live on the Linux Kernel Mailing List (LKML, https://lkml.org). Don't cite "Linus said X on GitHub" — cite the LKML thread.
  - Many famous "Linus quotes" are from forum/email posts decades old. Always link to the actual LKML archive URL.
- **Next verification step:**
  - WebFetch a specific recent LKML thread (e.g., a kernel release announcement) for one verifiable quote with archive URL
  - Cross-link kernel.org's "About Linus" page if it exists
- **Date verified:** 2026-05-27 (Claude session, WebFetch via gh CLI)
- **Reviewed by operator:** ⏳

### Steve Wozniak

- **Personal site (verified):** https://woz.org — "Officially Woz" branding, About + Woz Speaks + News sections (accessed 2026-05-27)
- **Maintenance signal (verified):** recent content dated April 2026 (AI commentary), January 2026 Pictet Bank interview, ongoing speaking engagement page
- **Topics covered (verified from site sections):** speaking engagements, news coverage of his appearances, WOZ-U technology training programs, photo galleries from events
- **Authoritative on:** early personal computer engineering (Apple I/II design), engineering simplicity and elegance, finishing projects under hardware constraints, the founder-engineer mindset
- **Visible pattern (verified):** site is curated more as a press/speaking hub than a technical blog — his deep technical writing lives in his autobiography "iWoz" (book, separate citation needed)
- **⚠️ Caveats:**
  - No technical blog posts surfaced from the homepage — this site is for booking/PR, not engineering writing
  - The "WOZ-U" branded education program ran into criticism years back; cite carefully if relevant (separate verification needed for current status)
- **Next verification step:**
  - For engineering principles, treat "iWoz" (the book) as the primary technical source, not the website
  - Verify any specific Wozniak quote against the book chapter/page, not website paraphrases
- **Date verified:** 2026-05-27 (Claude session, WebFetch — site live, technical content limited)
- **Reviewed by operator:** ⏳

### Dan Abramov

- **Personal site (verified):** https://overreacted.io — header reads "overreacted — A blog by Dan Abramov" with his photo (accessed 2026-05-27)
- **Topics covered (verified from recent posts):** React Server Components, web architecture, JS fundamentals (closures, hooks, classes), developer experience, technical communication craft
- **Recent verified posts (sample, accessed 2026-05-27):**
  - "A Social Filesystem" — 2026-01-18 (about formats over apps)
  - "Introducing RSC Explorer" — 2025-12-19 (hobby project)
  - "Hire Me in Japan" — 2025-11-11 (job search post)
  - "How to Fix Any Bug" — 2025-10-21 (on vibecoding)
- **Authoritative on:** React mental models (he was on the React core team), React Server Components, technical writing that explains hard concepts without oversimplifying
- **Visible pattern (verified from his post style):** explains complex topics conversationally, often with first-person reasoning shown ("I thought X, then realized Y"); blends technical depth with accessibility
- **⚠️ Caveats:**
  - "Hire Me in Japan" (Nov 2025) suggests he's in career-transition — his current employer is uncertain; verify before describing him as "React core team" today
- **Next verification step:** fetch his most-cited "explain hooks" post for a quote-anchored entry on React mental models
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Rich Harris

- **Canonical venue (verified):** https://svelte.dev/blog — Rich Harris identified as author of foundational Svelte posts ("Svelte 3: Rethinking reactivity", "Announcing SvelteKit 1.0") (accessed 2026-05-27)
- **Maintenance signal (verified):** monthly "What's new in Svelte" cadence active through May 2026 (Mar/Apr/May entries all present)
- **Authoritative on:** framework design philosophy (compile-time vs runtime, the "disappearing framework" idea), Svelte/SvelteKit architecture, web framework critique
- **Visible pattern (verified):** uses the official project blog as his primary tech writing venue (vs a separate personal blog); posts argue from first principles rather than benchmark numbers
- **⚠️ Caveats:**
  - This entry is anchored to the SVELTE blog, not a separate personal blog — his individual writing voice mixes with the official Svelte team voice on this URL
  - For quotes attributable strictly to Rich (not "the Svelte team"), look for posts byline-attributed to him specifically
- **Next verification step:**
  - WebFetch one Rich-bylined post (e.g., "Rethinking reactivity") for a direct verified quote on framework philosophy
  - Cross-check his X handle and personal site (if any) — not done in this session
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Guillermo Rauch

- **Canonical venue (verified):** https://github.com/rauchg — `gh api users/rauchg` returns name "Guillermo Rauch", company https://vercel.com, 16.9k followers, blog field → twitter.com/rauchg (accessed 2026-06-10)
- **Secondary venue (still unverified):** https://rauchg.com — HTTP 429 on three attempts across two sessions (2026-05-27 ×2, 2026-06-10)
- **Authoritative on:** Next.js architecture, edge runtime, developer experience, framework adoption strategy
- **⚠️ Caveats:**
  - Do NOT cite "rauchg.com says X" until that site fetches successfully — for essays, his X account or Vercel's blog (verified in companies-canonical.md) are the reachable primary channels
  - The GitHub verification confirms identity + affiliation, not specific essay content
- **Next verification step:** retry rauchg.com when the rate-limit window allows; anchor one specific essay
- **Date verified:** 2026-06-10 (Claude session, gh CLI — identity + affiliation; site content still pending)
- **Reviewed by operator:** ⏳

### David Heinemeier Hansson (DHH)

- **Personal site (verified):** https://world.hey.com/dhh — DHH's current blog on HEY (37signals's email product) (accessed 2026-05-27)
- **Role (verified from posts):** Co-owner and CTO of 37signals
- **Recent verified posts (sample, accessed 2026-05-27):**
  - "Basecamp Five" — 2026-05-26
  - "Celebrating computers at Omacon" — 2026-04-21
  - "The malleable computer" — 2026-04-15
  - "Panther Lake is the real deal" — 2026-04-06
  - "Basecamp becomes agent accessible" — 2026-03-25
- **Created (verified from his bio):** Ruby on Rails, Hotwire, Kamal, Omarchy
- **Books (verified mention):** REWORK, It Doesn't Have to Be Crazy at Work, REMOTE
- **Authoritative on:** Rails philosophy (convention over configuration, conceptual compression), opinionated framework design, remote-first work culture, anti-Big-Tech business stances
- **⚠️ Caveats:**
  - DHH's public stances are intentionally polemic — separate "DHH's opinion" from "industry consensus" when citing
  - His "Cloud Exit" (37signals leaving AWS) was a real and documented move but cite the specific blog post, not the meme version
- **Next verification step:** fetch one specific Rails-philosophy post (e.g., the original "Convention over configuration" framing) for a quote-anchored entry
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Andrej Karpathy

- **Personal site (verified):** https://karpathy.ai — accessed 2026-05-27
- **Featured projects (verified):** micrograd, char-rnn, arxiv-sanity, neuraltalk2, ConvNetJS
- **Bio (verified):** founding member at OpenAI (2015-17), Director of AI at Tesla (2017-22) leading Autopilot CV, returned to OpenAI (2023-24), currently producing educational AI content on YouTube
- **Famous writing (verified listed):** "A Recipe for Training Neural Networks", "The Unreasonable Effectiveness of Recurrent Neural Networks"
- **Teaching (verified):** Stanford CS 231n course on CNNs (he designed the first deep learning course at Stanford), recent YouTube lecture series on LLMs and AI
- **Authoritative on:** building neural nets from scratch (pedagogy via micrograd, makemore), the "Software 2.0" framing, ML training methodology, transformer internals
- **Visible pattern (verified):** teaches by re-building primitives from zero rather than starting from a framework; favors "do the simplest thing that works, then scale" over premature optimization
- **⚠️ Caveats:**
  - His YouTube series is current, but specific lecture timestamps shift as he updates — cite by video title + minute, not URL with `t=` if you can avoid it
  - His Twitter/X is active and influential but auth-walled to WebFetch
- **Next verification step:** fetch his "Recipe for Training Neural Networks" post for one quote-anchored entry on his methodology
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### John Carmack · ⚠️ PARTIAL VERIFICATION

- **Identified primary venue (unverified):** X / Twitter (@ID_AA_Carmack — heavily active there)
- **🚫 Verification status (2026-05-27):** PARTIAL — WebFetch to https://github.com/ID_AA_Carmack returned HTTP 404 (that handle is X-specific, not GitHub). Carmack does not maintain a public personal blog or website that we've verified — his primary writing venue today is X/Twitter, which is auth-walled to WebFetch.
- **Believed authoritative on (NOT verified from primary sources this session):** game engine architecture (Doom, Quake), VR/AR systems engineering (formerly Oculus CTO), working speed / focus rituals, AGI research (Keen Technologies, current role)
- **⚠️ Caveats:**
  - The .plan archive at https://github.com/ESWAT/john-carmack-plan-archive is now VERIFIED to exist (accessed 2026-06-10: community-maintained by ESWAT, 1.4k stars, README states it is a "Mirror of the John Carmack .plan Archive on floodyberry.com", organized by_day/by_year) — it is a MIRROR, not a primary source. Cite as "Carmack .plan of <exact date>, via community mirror" — never as "Carmack's site"
  - Files are 1996-2000s era; cite by exact .plan file date or specific X post URL — never paraphrase from memory
- **Next verification step:**
  - Identify whether Keen Technologies (his current company) publishes any blog/research — would be a true primary venue
  - His verified X account remains auth-walled to WebFetch
- **Date attempted:** 2026-05-27 (X auth-walled) · 2026-06-10 (mirror archive verified to exist, flagged as mirror)
- **Reviewed by operator:** ⏳

### Antirez (Salvatore Sanfilippo)

- **Personal site (verified):** https://antirez.com — accessed 2026-05-27
- **Recent verified posts (sample):**
  - "Distributing LLM inference in DwarfStar" — 2 days ago (Mac Studio + unified memory for local LLMs)
  - "Alternatives for the EDIT tool of LLM agents" — 8 days ago
  - "A few words on DS4" — 12 days ago (DwarfStar 4 local AI integration)
  - "Redis array type: short story of a long development" — 23 days ago (new Redis data structure, AI-assisted development)
  - "AI cybersecurity is not proof of work" — 41 days ago
- **Topics covered (verified from his posts):** AI/LLM inference + optimization, Redis architecture and development, distributed systems, programming philosophy / craftsmanship
- **Authoritative on:** Redis design (he wrote it), data structure design under hard performance constraints, C systems programming, the "small focused tool" engineering philosophy, recently — running LLMs on consumer hardware
- **Visible pattern (verified from his post titles):** writes about his hands-on experiments (DwarfStar series, Redis features being built); narrates the development process rather than presenting finished announcements
- **⚠️ Caveats:** he stepped back from Redis Labs years ago — current Redis features may not be his work; verify per-feature attribution
- **Next verification step:** fetch one specific Redis-design post for a verifiable quote on data structure philosophy
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Cassidy Williams

- **Personal site (verified):** https://cassidoo.co — accessed 2026-05-27
- **Current role (verified from site):** Senior Director of Developer Advocacy at GitHub
- **Self-described as:** startup advisor, investor, open source contributor, internet meme creator (also: mechanical keyboards, music, teaching)
- **Recent verified posts (sample):**
  - "A simple clustering algorithm for lists" — 2026-05-24 (sorting pattern she discovered organizing toys)
  - "La Pedra Go Club in Barcelona" — 2026-05-18 (travel)
  - "Shipping todometer, version 3!" — 2026-05-02 (personal app)
  - "Codemotion Madrid 2026 recap" — 2026-04-28
  - "Connecting the Logitech MX Creative Console to Elgato Lights" — 2026-04-13
- **Authoritative on:** developer advocacy at scale, making technical content accessible to broad developer audiences, the dev-influencer playbook, JavaScript / React for beginners
- **Visible pattern (verified from her post mix):** alternates technical posts with travel/personal posts; technical posts often pattern-mine from non-technical observations (the toy-sorting algorithm)
- **⚠️ Caveats:** her current GitHub Developer Advocacy role colors her positions on dev tools — note conflict of interest when citing her on GitHub features
- **Next verification step:** fetch one specific "how to teach JS" post for a quote-anchored entry on her pedagogical approach
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Patrick McKenzie (patio11)

- **Original blog (verified):** https://www.kalzumeus.com — older posts but still his canonical archive (accessed 2026-05-27)
- **Current primary venues (referenced from kalzumeus, NOT independently fetched this session):**
  - Newsletter: **Bits about Money** (https://www.bitsaboutmoney.com — needs separate verification fetch)
  - Podcast: **Complex Systems** (weekly)
- **Self-description (verified from site):** systems thinking applied to businesses; his "self-assigned score is median value created for software people times number of software people impacted"
- **Recent verified posts on kalzumeus (sample):**
  - "Bank CEO: Retract your debanking piece? Me: No." — 2025-02-10
  - "Tether's Troubles in November 2022" — 2022-11-11
  - "Tether Required Recapitalization In May 2022" — 2022-05-20
- **Topics covered (verified):** financial infrastructure and banking systems, cryptocurrency (skeptical), career advice for engineers, complex systems analysis, software business
- **Authoritative on:** technical communication for engineers (his "Salary Negotiation" guide is canonical), payments/banking infrastructure (he worked at Stripe for years), B2B SaaS sales
- **Visible pattern (verified):** writes long-form explainers that thread financial/operational expertise with engineering audience awareness; treats public blog posts as durable artifacts (some posts from 2010s still cited)
- **⚠️ Caveats:**
  - kalzumeus is no longer his daily venue — current writing is on Bits about Money. Cite the current venue when relevant.
  - Many older kalzumeus posts (~2013-era) about Japan + SaaS are still cited but represent a different career phase
- **Next verification step:** fetch https://www.bitsaboutmoney.com to verify it's live + add a "Current venue" section to this entry
- **Date verified:** 2026-05-27 (Claude session, WebFetch — kalzumeus verified, current venue deferred)
- **Reviewed by operator:** ⏳

---

## TODO — candidates pending verification

(All previously-listed candidates have been moved to Canonical or marked PARTIAL above. Operator's Mag7 list CLOSED at 6 on 2026-06-10 — all processed. Empty until new operator-suggested candidates land.)

---

## Format for canonical entries

```markdown
### <Full Name>

- **Personal site / canonical venue (verified):** <URL> — what identifies it (accessed YYYY-MM-DD)
- **Topics covered (verified from <source>):** ...
- **Recent verified posts:** ... (with URLs / dates)
- **Authoritative on:** ...
- **Visible patterns (verified):** ...
- **⚠️ Caveats:** ...
- **Next verification step:** ...
- **Date verified:** YYYY-MM-DD by Claude session, WebFetch
- **Reviewed by operator:** ⏳ / ✅
```

For partial-verification entries (URL identified, fetch blocked):
- Use header `### NAME · ⚠️ PARTIAL VERIFICATION`
- State the failure mode explicitly under `🚫 Verification status (date)`
- Document what was attempted and what's needed to complete verification

## Verification workflow (active)

1. Pick 1 candidate from TODO list
2. WebFetch each "Next verification step" URL
3. If URL returns the dev's actual content: ✅, write entry following format
4. If URL is dead / wrong / fabricated: note explicitly in the TODO row what failed
5. If URL is rate-limited / auth-walled: write PARTIAL entry per format above
6. Submit to operator for ratification
7. On approval: row moves from TODO to Canonical (or PARTIAL)
