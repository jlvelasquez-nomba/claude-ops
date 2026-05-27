# Companies — canonical engineering sources

**Status:** 🟢 ACTIVE · 11 canonical · 1 partial-verification · 0 TODO
**Per Rule #0 (active interpretation):** entries verified via WebFetch on date noted. Partial-verification entries are honest about what fetch failed and what to retry.

---

## Canonical entries

### Anthropic

- **Engineering blog / news (verified):** https://www.anthropic.com/news (accessed 2026-05-26)
- **Canonical domain (verified):** anthropic.com (footer + URL structure consistent)
- **Recent verified posts (sample, accessed 2026-05-26):**
  - "Introducing Claude Opus 4.7" — 2026-04-16 (anthropic.com/news/claude-opus-4-7)
  - "Anthropic acquires Stainless" — 2026-05-18 (anthropic.com/news/anthropic-acquires-stainless)
  - "Introducing Claude Design by Anthropic Labs" — 2026-04-17 (anthropic.com/news/claude-design-anthropic-labs)
  - "Project Glasswing" — 2026-04-07 (anthropic.com/glasswing)
- **Responsible Scaling Policy (verified link from footer):** https://www.anthropic.com/news/announcing-our-updated-responsible-scaling-policy
- **Topic coverage (verified from newsroom structure):**
  - Models / products (Claude variants — Opus, Sonnet, Haiku, Claude Code, Design tools)
  - Safety & responsibility (RSP, Constitutional AI)
  - Research (Project Glasswing — software security; AI usage studies)
  - Partnerships (KPMG, PwC, Gates Foundation, AWS, Google, Microsoft)
  - Enterprise (financial services, government, healthcare, legal)
- **Authoritative on:** LLM training methodology, AI safety / responsible scaling, agentic tool use design, prompt caching, model evals
- **⚠️ Caveats:**
  - Newsroom posts are PR/announcement-focused; deeper technical content lives in their research papers (separate URLs, not all fetched yet)
  - As of this fetch, "Constitutional AI" referenced but the canonical paper URL not surfaced — need separate fetch of research index
- **Next verification step:**
  - WebFetch https://www.anthropic.com/research for canonical paper list
  - Verify a specific RSP claim with the policy doc itself
- **Date verified:** 2026-05-26 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### OpenAI · ⚠️ PARTIAL VERIFICATION

- **🚫 Verification status (2026-05-27):** PARTIAL — Both https://platform.openai.com/docs and https://openai.com (root) returned HTTP 403 to WebFetch (bot-walled). The main site exists in public knowledge but content not confirmable from this session via WebFetch.
- **Verified alternative venue:** https://github.com/openai/openai-cookbook (accessed 2026-05-27 via `gh repo view`) — "Examples and guides for using the OpenAI API", points to https://cookbook.openai.com as the published rendering
- **Authoritative on (verified from cookbook repo):** practical OpenAI API patterns, evaluation harnesses, fine-tuning recipes, function calling patterns
- **⚠️ Caveats:**
  - For research papers, the platform docs page is the canonical source but WebFetch can't reach it — cite specific paper URLs (e.g., GPT-4 technical report) directly when needed
  - Do NOT cite "openai.com says X" from memory — until a successful fetch, restrict citations to the cookbook repo or specific paper PDFs
- **Next verification step:**
  - Try alternative venues: WebFetch https://cookbook.openai.com (the published version of the cookbook repo)
  - Try the OpenAI Help Center (help.openai.com)
  - Or rely on the cookbook + specific paper URLs as authoritative
- **Date attempted:** 2026-05-27 (main site 403; cookbook verified via gh CLI)
- **Reviewed by operator:** ⏳

### Google SRE (sre.google)

- **Engineering site (verified):** https://sre.google (accessed 2026-05-27) — "SRE is what you get when you treat operations as if it's a software problem"
- **Canonical books listed (verified):**
  - **Site Reliability Engineering** (the original SRE book) — accessible via /sre-book/table-of-contents/
  - **The Site Reliability Workbook** — accessible via /workbook/table-of-contents/
  - **Building Secure & Reliable Systems**
- **Other resources (verified from site):** SRE Fundamentals course, The Art of SLO classroom, SRE Video Gallery, Prodcast (SRE podcast), Museum of Borgmon Abstract Art, Measuring Reliability, Product-Focused Reliability, System Theoretic Process Analysis
- **Authoritative on:** SRE methodology (error budgets, SLI/SLO/SLA, blameless postmortems), large-scale reliability engineering, the operator-as-software-engineer cultural model
- **⚠️ Caveats:**
  - Direct chapter URLs to specific SRE book chapters were NOT listed on the index page — need to fetch the TOC to enumerate them
  - "Postmortem Culture" chapter (Ch. 15 of the original SRE book) is cited in our primary-sources.md — see that file for the canonical chapter URL
- **Next verification step:** WebFetch /sre-book/table-of-contents/ to enumerate the 26 chapter URLs as named anchors
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Stripe

- **Engineering blog (verified):** https://stripe.com/blog/engineering (accessed 2026-05-27)
- **Recent verified posts (sample):**
  - "Can AI agents build real Stripe integrations? We built a benchmark to find out" — 2026-03-02
  - "How we built it: Real-time analytics for Stripe Billing" — 2025-09-16
  - "How we built it: Jurisdiction resolution for Stripe Tax" — 2025-07-10
  - "How Stripe's document databases supported 99.999% uptime with zero-downtime data migrations" — 2024-06-06
  - "Test clocks: How we made it easier to test Stripe Billing integrations" — 2024-05-09
- **Topic coverage (verified from post mix):** AI agent benchmarking, payment systems, real-time analytics, database infrastructure (99.999% uptime patterns), developer tooling for testing
- **Authoritative on:** payments API design, financial infrastructure at scale, API/SDK developer experience, zero-downtime database migrations, idempotency patterns
- **Visible pattern (verified):** "How we built it" series presents real architecture with named tradeoffs — these are technical post-mortems, not marketing posts
- **⚠️ Caveats:**
  - Cadence has slowed in 2025-2026 — verify the latest post date before citing the blog as "current"
- **Next verification step:** fetch the "How we built it" series index for the full archive of architecture posts
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Cloudflare

- **Engineering blog (verified):** https://blog.cloudflare.com (accessed 2026-05-27) — "Get the latest news on how products at Cloudflare are built"
- **Recent verified posts (sample):**
  - 2026-05-21 — Claude Compliance API integration with Cloudflare CASB
  - 2026-05-19 — Claude Managed Agents on Cloudflare
  - 2026-05-18 — Project Glasswing security-focused LLM analysis
  - 2026-05-14 — ClickHouse performance bottleneck investigation
  - 2026-05-13 — Browser Run rebuilt on Cloudflare Containers
- **Topic coverage (verified from post mix):** AI agents/orchestration (currently dominant), edge computing (Workers), security (Glasswing, QUIC fixes, Linux vulns), DNS reliability
- **Authoritative on:** edge computing architecture (Workers / Durable Objects / R2), DDoS mitigation at scale, network security operations, "Innovation Week" cadence for product announcements
- **Visible pattern (verified):** very high cadence (multiple posts/day), real-time engineering deep-dives for incident reports, heavy emphasis on AI infra in 2026
- **⚠️ Caveats:**
  - Distinguish product announcements (marketing-heavy) from incident post-mortems (technically deep) — the blog mixes both
- **Next verification step:** fetch the "Outage / post-mortem" tag for the authoritative incident-analysis archive
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Vercel

- **Engineering blog (verified):** https://vercel.com/blog (accessed 2026-05-27) — "The Vercel blog covers engineering, product updates, and customer stories"
- **Recent verified posts (sample):**
  - 2026-05-12 — "AI Gateway production index" (data from production AI traffic)
  - 2026-05-10 — "How Superset built the IDE for AI agents on Vercel"
  - 2026-05-05 — "How KIKO Milano scales for Black Friday"
  - 2026-05-04 — "How General Intelligence used agents to build an agent platform on Vercel"
  - 2026-05-04 — "Introducing deepsec: The security harness for finding vulnerabilities"
- **Topic coverage (verified):** AI agents (overwhelmingly dominant in 2026), Next.js releases, edge computing, e-commerce case studies, security tooling
- **Authoritative on:** Next.js (they own the framework), edge runtime / ISR (incremental static regeneration), CDN/build infrastructure, AI gateway design patterns
- **Visible pattern (verified):** customer stories interleave with product/framework announcements; technical depth varies
- **⚠️ Caveats:**
  - Customer-story posts can be marketing-shaped — for canonical Next.js architecture, prefer the official Next.js docs (separately verified at nextjs.org/docs/llms.txt)
  - Verify Next.js version + behavior claims against the docs, not blog posts that may describe older versions
- **Next verification step:** fetch one specific "AI Gateway" architectural post for a quote-anchored citation on their gateway design
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Supabase

- **Engineering blog (verified):** https://supabase.com/blog (accessed 2026-05-27)
- **Recent verified posts (sample):**
  - 2026-05-26 — "Protecting your Supabase projects from npm supply chain attacks"
  - 2026-05-08 — "Supabase Is Now an Official ChatGPT App"
  - 2026-05-06 — "Introducing @supabase/server"
  - 2026-05-05 — "Realtime or ETL? How to choose the right tool"
  - 2026-05-04 — "Branching Without Git Is Now The Default"
- **Topic coverage (verified):** product features and integrations, security (npm supply chain, ISO 27001), AI/ChatGPT integrations, realtime, developer tools
- **Authoritative on:** Postgres-as-a-service architecture, Row Level Security (RLS) patterns, realtime subscription design, vector embeddings + pgvector
- **Visible pattern (verified):** blog skews toward product announcements; deep technical content (RLS, vector, Postgres internals) lives in /docs not /blog
- **⚠️ Caveats:**
  - For RLS, vector, or foundational Postgres patterns, prefer https://supabase.com/docs over the blog (the blog mentions features, the docs explain them)
  - Their llms-full.txt corpus (verified separately in coding-wikis-troubleshooting.md) is the highest-density source for LLM citations
- **Next verification step:** fetch one specific RLS-architecture post or doc page for a quote-anchored entry
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Netflix

- **Engineering blog (verified):** https://netflixtechblog.medium.com (accessed 2026-05-27) — Medium-hosted, 458K followers
- **Note:** the bare domain `netflixtechblog.com` returned an SSL certificate error in this session; the Medium subdomain works and is the same content
- **Recent verified posts (sample):**
  - May 18 — "The Evolution of Cassandra Data Movement at Netflix" (Guil Pires et al.)
  - May 11 — "Data Projects: Managing Data Assets at Netflix Scale" (Amer Hesson et al.)
  - May 8 — "Scaling ArchUnit with Nebula ArchRules" (John Burns and Emily Yuan)
  - May 4 — "Democratizing Machine Learning at Netflix: Building the Model Lifecycle Graph"
  - May 1 — "State of Routing in Model Serving"
- **Topic coverage (verified):** data infrastructure (Cassandra at scale), ML model lifecycle and serving, scalability patterns, codebase governance (ArchUnit)
- **Authoritative on:** streaming infrastructure at scale, chaos engineering (Chaos Monkey originated here), microservices observability, ML platform engineering
- **Visible pattern (verified):** posts are bylined by named engineers (not "Netflix Team") — high attribution, often signals named authority on specific subsystems
- **⚠️ Caveats:**
  - The bare `netflixtechblog.com` domain had SSL issues this session — always use the Medium subdomain for fetches
- **Next verification step:** verify the `netflixtechblog.com` SSL cert issue is transient (try again in a future session); meanwhile use Medium subdomain
- **Date verified:** 2026-05-27 (Claude session, WebFetch via Medium subdomain)
- **Reviewed by operator:** ⏳

### Shopify

- **Engineering blog (verified):** https://shopify.engineering (accessed 2026-05-27)
- **Recent verified posts (sample):**
  - 2026-05-12 — "We replaced Redis with MySQL for inventory reservations—and it scaled" (Infrastructure)
  - 2026-04-22 — "Flow generation through natural language: An agentic modeling approach" (AI/ML)
  - 2026-04-15 — "Autoresearch isn't just for training models" (AI/ML)
  - 2026-03-19 — "Building a Magic Mirror: AI retail experiences with Remix" (AI/ML)
  - 2026-03-12 — "Shopify's journey to faster breadth-first GraphQL execution" (Development)
- **Topic coverage (verified):** AI/ML applications in e-commerce (dominant in 2026), infrastructure and database optimization (Redis→MySQL migration), Rails at scale, GraphQL performance
- **Authoritative on:** Rails monolith at massive scale, e-commerce platform architecture, MySQL/Redis trade-offs at scale, GraphQL execution optimization, Shopify Plus enterprise patterns
- **Visible pattern (verified):** "We replaced X with Y" pattern signals real architectural changes with documented results; very high-signal-to-noise ratio
- **⚠️ Caveats:**
  - Posts often describe Shopify-specific scale (10s of thousands of merchants) — generalize cautiously to smaller systems
- **Next verification step:** fetch the Redis→MySQL post for a quote-anchored citation on their architecture decision
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### GitHub

- **Engineering blog (verified):** https://github.blog/engineering (accessed 2026-05-27)
- **Recent verified posts (sample):**
  - 2026-05-14 — "From latency to instant: Modernizing GitHub Issues navigation performance"
  - 2026-04-16 — "How GitHub uses eBPF to improve deployment safety"
  - 2026-04-03 — "The uphill climb of making diff lines performant"
  - 2026-03-31 — "Agent-driven development in Copilot Applied Science"
  - 2026-03-12 — "Continuous AI for accessibility: How GitHub transforms feedback into inclusion"
- **Topic coverage (verified):** performance optimization, Copilot / AI features (agent-driven dev, accessibility), infrastructure and deployment safety (eBPF), user experience
- **Authoritative on:** Git workflows at platform scale, Codespaces architecture, GitHub Actions runner design, Copilot's IDE integration patterns
- **Visible pattern (verified):** mixes performance engineering deep-dives ("uphill climb of diff lines") with Copilot product narratives; both bylined
- **⚠️ Caveats:**
  - GitHub's content is split across github.blog (engineering + product) and docs.github.com (reference) — cite the right venue per claim type
- **Next verification step:** fetch one specific Copilot architecture post for a quote-anchored citation on their agent design
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### HashiCorp

- **Engineering blog (verified):** https://www.hashicorp.com/blog (accessed 2026-05-27) — "The Stack"
- **Recent verified posts (sample):**
  - 2026-05-20 — "Encrypting large artifacts and streaming workloads with Vault"
  - 2026-05-19 — "Azure hub-and-spoke generally available for HCP Vault Dedicated"
  - 2026-05-14 — "The great AI divide: Why early leaders embrace an AI operating model"
  - 2026-05-13 — "New in Terraform 1.15: Dynamic sources, variable deprecation, and more"
  - 2026-05-12 — "Announcing native AI agent support in HashiCorp Vault"
- **Product/topic categories (verified):** Vault (secrets management + AI agent support), Terraform (IaC, enterprise features), Packer (image building, SBOM scanning), Boundary (secure remote access), Consul (service networking), plus AI/agentic systems and platform engineering
- **Authoritative on:** infrastructure-as-code patterns (Terraform language + module design), secrets management at enterprise scale, service mesh architecture (Consul), provisioning workflows
- **Visible pattern (verified):** product-release-focused posts (Terraform 1.15, Vault features) — cite by product+version, never just "HashiCorp says X"
- **⚠️ Caveats:**
  - HashiCorp is now an IBM company (acquired 2024) — internal positioning may shift over time
  - Mitchell Hashimoto (co-founder, separately canonical in developers-canonical.md) departed years ago; cite him separately from current company positions
- **Next verification step:** fetch one Terraform release notes post for a verifiable specific feature claim
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

### Discord

- **Engineering blog (verified):** https://discord.com/category/engineering (accessed 2026-05-27)
- **Recent verified posts (sample):**
  - "How Discord Automates ScyllaDB Clusters at Scale" — 2024 (still featured)
  - "Behind the Scenes of the 3/25/26 Voice Outage" — 2026
  - "Measure Less to Learn More" — 2024
  - "Building on the Social Layer of Games: What's New from GDC 2026"
  - "Tracing Discord's Elixir Systems (Without Melting Everything)" — 2024
- **Topic coverage (verified):** infrastructure and scalability (ScyllaDB clusters, voice infra), Elixir + Rust backend, game developer integrations, voice/video encryption (DAVE), incident post-mortems
- **Authoritative on:** real-time chat infra at massive scale (Discord has 200M+ MAU), Elixir/OTP in production, Rust adoption for performance-critical paths, voice/video encryption design
- **Visible pattern (verified):** incident post-mortems are deeply technical (Voice Outage post); they don't hide engineering details when things break
- **⚠️ Caveats:**
  - Cadence is irregular — months between posts in some periods. Don't infer "recent" from the post being on the front page; check the date
- **Next verification step:** fetch the Voice Outage 2026-03-25 post for a quote-anchored citation on their incident response process
- **Date verified:** 2026-05-27 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳

---

## TODO — candidates pending verification

(All previously-listed candidates have been moved to Canonical or marked PARTIAL above. Empty until new operator-suggested candidates land — see operator's Mag7 / Tesla / xAI list, pending names from Juan.)

---

## Format for canonical entries

See Anthropic entry above as worked example. Required: verified URL, accessed date, recent verified posts, authoritative topics, caveats, next verification step.

For partial-verification entries (URL identified, fetch blocked):
- Use header `### NAME · ⚠️ PARTIAL VERIFICATION`
- State the failure mode explicitly under `🚫 Verification status (date)`
- Document what was attempted and what's needed to complete verification

## Verification workflow

1. Pick 1 candidate from TODO list
2. WebFetch their primary engineering URL
3. If returns real content: write entry following Anthropic example
4. If dead / wrong: document what failed in the TODO row
5. If rate-limited / auth-walled: write PARTIAL entry per format above
6. Operator review + promote to Canonical (or PARTIAL)
