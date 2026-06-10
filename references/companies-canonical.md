# Companies — canonical engineering sources

**Status:** 🟢 ACTIVE · 18 canonical · 0 partial-verification · 0 TODO
**Per Rule #0 (active interpretation):** entries verified via WebFetch on date noted. Partial-verification entries are honest about what fetch failed and what to retry.

---

## Canonical entries

### Apple (developer org) · operator-specified

- **Dev portal (verified):** https://developer.apple.com/ (accessed 2026-06-10) — WWDC26 featured, platforms iOS/iPadOS/macOS/tvOS/visionOS/watchOS 27, agent-centric sessions ("Xcode, agents, and you", "Debug and profile agentic experiences")
- **Documentation (title-verified):** https://developer.apple.com/documentation/ — "Featured | Apple Developer Documentation"; content is JS-rendered, framework list not extractable via WebFetch
- **Forums (verified):** https://developer.apple.com/forums/ — 16 topic categories confirmed (UI Frameworks, ML & AI, Spatial Computing, Design, etc.)
- **Design hub (verified):** https://developer.apple.com/design/ — headline "Design incredible apps and games that integrate seamlessly with Apple platforms"; lists HIG, Apple Design Resources (official Figma/Sketch templates), SF Symbols (7,000+ symbols), Icon Composer, Design Awards
- **HIG (title-verified):** https://developer.apple.com/design/human-interface-guidelines — "Human Interface Guidelines | Apple Developer Documentation"; body JS-rendered
- **Authoritative on:** Apple platform APIs, design-system governance (HIG + resources + symbol library), developer community structure
- **⚠️ Caveats:** documentation + HIG body content is JS-walled to WebFetch — title-level verification only; for specific HIG claims, fetch the specific subsection URL or label as unverified
- **Date verified:** 2026-06-10 (Claude session, WebFetch ×5)
- **Reviewed by operator:** ⏳ (sources supplied by operator 2026-06-10)

### NVIDIA (developer org) · operator-specified

- **Dev portal (verified):** https://developer.nvidia.com/ (accessed 2026-06-10) — CUDA Toolkit 13.1, TensorRT 10 under Latest Releases; topics: AI, Graphics & Rendering, HPC, Autonomous Vehicles
- **Forums (verified):** https://forums.developer.nvidia.com/ — categories AI & Data Science, Gaming and Visualization, Omniverse
- **Downloads (verified):** https://developer.nvidia.com/downloads — NGC hub + per-domain SDKs (CUDA Toolkit, HPC SDK, Jetson, Isaac, Clara, DRIVE, Riva, Omniverse)
- **Training (verified):** https://www.nvidia.com/en-us/training/ — Deep Learning Institute: self-paced + instructor-led + certifications; "Access to fully configured, GPU-accelerated servers in the cloud" for hands-on practice
- **CUDA C++ Best Practices Guide (verified, quote-anchored):** https://docs.nvidia.com/cuda/cuda-c-best-practices-guide/index.html (v13.3) — APOD cycle (Assess → Parallelize → Optimize → Deploy): *"a cyclical process: initial speedups can be achieved, tested, and deployed with only minimal initial investment of time, at which point the cycle can begin again by identifying further optimization opportunities."*
- **Authoritative on:** GPU/accelerated computing, performance optimization methodology (APOD), developer education at scale (DLI)
- **Date verified:** 2026-06-10 (Claude session, WebFetch ×5)
- **Reviewed by operator:** ⏳ (sources supplied by operator 2026-06-10)

### Meta (engineering org) · operator-specified

- **Engineering blog (verified):** https://engineering.fb.com/ (accessed 2026-06-10) — recent posts confirmed: "Lights Out, Systems On" (2026-06-03), "SilverTorch: Index as Model" (2026-05-26), "Reel Friends" (2026-05-13)
- **Key post (verified, quote-anchored):** https://engineering.fb.com/2023/02/06/ios/facebook-ios-app-architecture/ — "The evolution of Facebook's iOS app architecture" (2023-02-06). Verified arc: ComponentKit declarative UI (2014, React-inspired) → dylib-based modular architecture (2016, against ~30s launch times) → Buck-generated plugin system (2018) that *"moved error detection from runtime to compile-time"*
- **Flux (verified via gh API):** https://github.com/facebookarchive/flux — 17.5k stars, "Application Architecture for Building User Interfaces". **ARCHIVED** (last push 2023-03) — historical reference for unidirectional data flow, not a living project
- **Authoritative on:** large-scale app architecture evolution, compile-time safety at thousands-of-engineers scale, declarative UI lineage (ComponentKit/React/Flux)
- **⚠️ Caveats:**
  - Flux is archived — cite as the historical origin of the unidirectional pattern, point to modern successors for current practice
  - Two operator-supplied academic papers on Facebook architecture live in `references/primary-sources.md` with PARTIAL status (First Monday title-verified; ACM DOI 403-walled)
  - Operator-supplied third party (verified as third-party, tier B): codekarle.com Facebook system design — educational breakdown by Daub Technovision, NOT Meta content; useful for interview-style component maps, never citable as "how Facebook works"
- **Date verified:** 2026-06-10 (Claude session, WebFetch ×3 + gh API)
- **Reviewed by operator:** ⏳ (sources supplied by operator 2026-06-10)

### Alphabet — Google Cloud & YouTube (developer org) · operator-specified

- **Well-Architected Framework (verified, quote-anchored):** https://docs.cloud.google.com/architecture/framework (accessed 2026-06-10, es-419) — *"proporciona recomendaciones para ayudar a arquitectos, desarrolladores, administradores y otros profesionales de la nube a diseñar y operar una topología en la nube que sea segura, eficiente, resiliente, de alto rendimiento, rentable y sustentable."* Six pillars: operational excellence, security/privacy/compliance, reliability, cost optimization, performance optimization, sustainability (+ AI/ML cross-pillar perspective)
- **Architecture Center hub (verified):** https://docs.cloud.google.com/architecture — note: the operator-supplied `?category=aiandmachinelearning` URL lands on the unfiltered hub; AI/ML is a category selected in-page
- **Enterprise application blueprint (verified):** https://docs.cloud.google.com/architecture/blueprints/enterprise-application-blueprint/architecture — multi-region GKE, three environments, immutable containers, Binary Authorization, workload identity federation
- **YouTube developer docs (verified):** https://developers.google.com/youtube/documentation — Data API, Live Streaming, Analytics, Reporting, Content ID, IFrame Player
- **Data architecture explainer (title-verified):** https://cloud.google.com/discover/what-is-data-architecture — "¿Qué es la arquitectura de datos? | Google Cloud"; body truncated in fetch
- **Authoritative on:** cloud architecture review methodology (six pillars), reference blueprints, YouTube platform APIs
- **⚠️ Caveats — operator-supplied third-party/tertiary sources (verified as such, tier B; never cite as official):**
  - geeksforgeeks.org YouTube system design — third-party educational reconstruction (CDN/DASH/Kafka/Cassandra component map), not Google architecture docs
  - greenware-tech.com YouTube languages post — third-party blog, no citations to official sources
  - Wikipedia "Programming languages used in most popular websites" — tertiary; lists YouTube backend as Python/C/C++/Java/Go with Vitess/BigTable/MariaDB; usable as a pointer to its primary citations, not as the source itself
- **Note:** Google SRE (sre.google) has its own separate canonical entry above
- **Date verified:** 2026-06-10 (Claude session, WebFetch ×8)
- **Reviewed by operator:** ⏳ (sources supplied by operator 2026-06-10)

### Amazon — AWS (developer org) · operator-specified

- **Architecture Center (verified):** https://aws.amazon.com/architecture/ (accessed 2026-06-10) — "Reference Architecture Examples and Best Practices"; offers Well-Architected framework, reference architectures, diagrams, decision guides (ML, analytics, containers, storage, networking), whitepapers
- **Well-Architected pillars (verified):** *"six pillars—operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability"*
- **Authoritative on:** reference-architecture-first design, decision guides, the Well-Architected review model
- **Triangulation note:** AWS's six pillars and Google Cloud's six pillars converge almost exactly (independently published) — strong cross-vendor triangulation for pillar-based architecture review (per `protocols/triangulate-references.md`, this is the ≥2-primary-sources bar met for "industry standard")
- **Date verified:** 2026-06-10 (Claude session, WebFetch)
- **Reviewed by operator:** ⏳ (source supplied by operator 2026-06-10)

### Microsoft (developer org) · operator-specified

- **Dev portal (verified):** https://developer.microsoft.com/en-us/microsoft-365 (accessed 2026-06-10) — "Microsoft 365 Dev Center | Build intelligent experiences", headline "Reimagine the way people work". Platform areas: Microsoft 365 Copilot (agents), Teams, Microsoft Graph, Mesh, SharePoint Framework (SPFx).
- **Video channel (verified via yt-dlp, 2026-06-10):** https://www.youtube.com/microsoftdeveloper — channel "Microsoft Developer" (@MicrosoftDeveloper, id UCsMica-v34Irf9KVTh6xx-g), 684k subscribers. Recent titles confirm agent-centric focus: "Work IQ: A2A for Context-Aware, Agentic Experiences", "Your agent anywhere: MultiClient MultiDevice with GitHub Copilot SDK", plus an open-sourcing-history session (TypeScript, .NET, VS Code, Copilot extension).
- **Verified developer-program structure:** Microsoft 365 Developer Program (free renewable sandbox subscription **pre-configured with sample data**), Technology Adoption Program (early roadmap access + product-group feedback), PnP Community.
- **Authoritative on:** M365/Copilot agent platform, Teams/Graph integration patterns, developer-onboarding program design at scale
- **⚠️ Caveats:**
  - The YouTube page is consent-walled to WebFetch (302 to consent.youtube.com) — verification was via yt-dlp metadata; re-verify the same way
  - Dev Center copy is marketing-toned; for API-level claims cite learn.microsoft.com docs pages (not yet fetched — separate verification when needed)
- **Next verification step:** anchor one specific Learn docs page when a protocol cites a Microsoft API pattern
- **Date verified:** 2026-06-10 (Claude session, WebFetch + yt-dlp)
- **Reviewed by operator:** ⏳ (sources supplied by operator 2026-06-10)

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

### OpenAI

- **Canonical venue (verified):** https://developers.openai.com/cookbook — the OpenAI Cookbook web rendering (accessed 2026-06-10; cookbook.openai.com 308-redirects here). Sample verified guide titles: "Build an Agent Improvement Loop with Traces, Evals, and Codex", "Build iterative repair loops with Codex", "How Perplexity Brought Voice Search to Millions Using the Realtime API". Topics: Agents, Evals, Multimodal, Text, Guardrails, Optimization.
- **Canonical repo (verified):** https://github.com/openai/openai-cookbook — `gh api`: 74.1k stars, pushed 2026-06-10, "Examples and guides for using the OpenAI API". Org verified: `gh api orgs/openai` → 255 public repos.
- **Authoritative on:** practical OpenAI API patterns, agent/eval harnesses, fine-tuning recipes, function calling patterns
- **⚠️ Caveats:**
  - https://openai.com (root) and /research remain HTTP 403 to WebFetch (retried 2026-06-10) — for research claims, cite specific paper URLs/PDFs directly, NOT "openai.com says X" from memory
  - Scope of this canonical entry = cookbook + GitHub org (engineering/API patterns), not company research/PR positions
- **Next verification step:** anchor one specific cookbook guide URL when a protocol cites an OpenAI pattern
- **Date verified:** 2026-06-10 (Claude session, WebFetch on developers.openai.com/cookbook + gh CLI; root site still bot-walled)
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
