# Companies — canonical engineering sources

**Status:** 🟢 ACTIVE · 1 canonical · 11 TODO
**Per Rule #0 (active interpretation):** entries verified via WebFetch on date noted. Empty NOT acceptable as end state.

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

## TODO — candidates pending verification

| Candidate | Topics authoritative | Next verification step | Status |
|---|---|---|---|
| OpenAI | LLM eval, cookbook patterns | WebFetch platform.openai.com/docs + github.com/openai/openai-cookbook | TODO |
| Google SRE (sre.google) | reliability, error budgets, postmortems | Already partial — see primary-sources.md for chapter URLs | TODO (partial) |
| Stripe | payments, API design, dev experience | WebFetch stripe.com/blog/engineering | TODO |
| Cloudflare | edge networking, security | WebFetch blog.cloudflare.com (engineering tag) | TODO |
| Vercel | Next.js, edge runtime, DX | WebFetch vercel.com/blog | TODO |
| Supabase | Postgres at scale, RLS, realtime | WebFetch supabase.com/blog | TODO |
| Netflix | streaming infra, chaos engineering | WebFetch netflixtechblog.com | TODO |
| Shopify | Rails at scale, e-commerce | WebFetch shopify.engineering | TODO |
| GitHub | git workflows, scale, dev infra | WebFetch github.blog (engineering tag) | TODO |
| HashiCorp | infra as code, Terraform patterns | WebFetch hashicorp.com/blog | TODO |
| Discord | scaling chat infra, voice | WebFetch discord.com/blog/engineering | TODO |

## Format for canonical entries

See Anthropic entry above as worked example. Required: verified URL, accessed date, recent verified posts, authoritative topics, caveats, next verification step.

## Verification workflow

1. Pick 1 candidate from TODO list
2. WebFetch their primary engineering URL
3. If returns real content: write entry following Anthropic example
4. If dead / wrong: document what failed in the TODO row
5. Operator review + promote to Canonical
