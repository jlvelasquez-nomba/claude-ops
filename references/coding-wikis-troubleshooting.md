# Coding Wikis — Troubleshooting References

**Per Rule #0:** every URL below was verified `curl -L -o /dev/null -w "%{http_code}"` returning 200 on 2026-05-27. If a future fetch returns 404, mark it broken — don't paraphrase from memory.

This file is scoped to **the actual stack we use** in `nomba-content-engine`, `jarvis/video-starter`, and `supra-crm`. Libraries we don't depend on aren't here. When a new framework joins the stack, verify its docs and add a row.

---

## Section A — Frameworks with official `llms.txt` (use these first)

`llms.txt` is a machine-readable docs index published by the framework's own maintainers. When present, it overrides whatever's in my training data.

| Library | Used in | Verified `llms.txt` URL |
|---|---|---|
| **Next.js** (`next@16.2.4`) | content-engine | https://nextjs.org/llms.txt (also `/docs/llms.txt`) |
| **React** (`react@18.3` / `react@19.2`) | jarvis · content-engine · supra-crm | https://react.dev/llms.txt |
| **Supabase JS** (`@supabase/supabase-js`) | content-engine · supra-crm | https://supabase.com/llms.txt (and `https://supabase.com/llms-full.txt` for full corpus) |
| **Vite** (`vite@8.0.4`) | supra-crm | https://vite.dev/llms.txt |
| **Vitest** (`vitest@3.x` / `vitest@4.x`) | content-engine · supra-crm | https://vitest.dev/llms.txt |
| **Zod** (`zod@3` / `zod@4`) | all three repos | https://zod.dev/llms.txt |
| **Remotion** (`remotion@4.0.457`) | jarvis | https://remotion.dev/llms.txt |
| **Fastify** (`fastify@5.2`) | jarvis | https://fastify.dev/llms.txt |
| **TanStack** (Query / Table / Virtual) | supra-crm | https://tanstack.com/llms.txt (+ project root https://tanstack.com/) |
| **Sentry** (`@sentry/node`, `@sentry/react`) | supra-crm | https://docs.sentry.io/llms.txt |
| **shadcn/ui** | content-engine | https://ui.shadcn.com/llms.txt |
| **Claude Code + Anthropic API** | reference | https://code.claude.com/docs/llms.txt · https://docs.anthropic.com/en/llms.txt · https://platform.claude.com/docs/llms.txt |

---

## Section B — Frameworks WITHOUT `llms.txt` (use the official docs root)

These maintainers don't publish a machine-readable index (verified 404 on 2026-05-27). Use the canonical docs URL instead.

| Library | Used in | Canonical docs URL |
|---|---|---|
| **Tailwind CSS** (`tailwindcss@4`) | content-engine · supra-crm | https://tailwindcss.com/docs |
| **Radix UI** (`@radix-ui/*`) | content-engine · supra-crm | https://www.radix-ui.com/primitives/docs |
| **OpenAI SDK** (`openai@6`) | content-engine | https://platform.openai.com/docs/api-reference |
| **Motion / Framer Motion** (`framer-motion@12`) | supra-crm | https://motion.dev/docs/ai-kit (operator-recommended LLM-oriented entry point) |
| **Node.js** (runtime) | all | https://nodejs.org/api — also check API stability tag (0/1/2/3); do NOT use Stability 0 or 1 in production |

---

## Section C — General-purpose references

| What | URL |
|---|---|
| **MDN Web Docs** — JS, TS, CSS, HTML, all Web APIs | https://developer.mozilla.org/en-US/ |
| **React API reference** — every hook + element with examples | https://react.dev/reference/react |
| **Tailwind community wiki** (curated by `andrewmcodes`, archived but useful) | https://github.com/andrewmcodes-archive/notes-wiki/blob/master/tailwind-css.md |

**MDN rules:**
- ✅ Always check the **Browser compatibility** table at the bottom of every MDN page before relying on an API
- ✅ Prefer MDN over Stack Overflow for any Web API question (Mozilla / Google / Apple / Microsoft contribute directly to MDN)
- ❌ Do not use W3Schools as a substitute — it lags the spec and contains errors

---

## Section D — General coding-practice guides (operator-supplied, verified 2026-06-10)

| What | URL | Tier |
|---|---|---|
| **MIT/Broad CommLab — Best Practices for Coding, Organization, and Documentation** (Broad Research Communication Lab, Broad Institute of MIT & Harvard). Verified quote: *"Keeping in mind the needs of your audience – that is, either your future self or anyone else who might want to reuse your code – will help you to create concise, readable, and reusable code"* | https://mitcommlab.mit.edu/broad/commkit/best-practices-for-coding-organization-and-documentation/ | A (institutional) |
| **DataCamp — Coding Best Practices: A Complete Guide (2026)** — commercial tutorial covering structure, docs, testing, security, AI-assisted dev. Useful checklist, not a standard | https://www.datacamp.com/tutorial/coding-best-practices-and-guidelines | B (commercial tutorial) |

---

## Protocol — how to use these references mid-session

1. **Before writing code with a framework** → fetch its row from Section A or B. Note the version it documents. Confirm it matches `package.json`. If mismatch, flag the operator before coding.
2. **When I hit an error I can't resolve internally** → identify the layer (browser API → MDN; Node runtime → Node docs; framework → its `llms.txt` or docs URL). Fetch the relevant page. Cite the exact URL and section. Do not paraphrase from training data.
3. **When docs contradict what I expected** → the docs win, always. Update my memory + this file if a behavior changed.
4. **When verifying claims** — Rule #0 — `curl -L -o /dev/null -w "%{http_code}" -A "Mozilla/5.0" --max-time 10 <URL>` returns the real HTTP status. WebFetch's summarization can mislead on whether a file actually exists.

---

## Verification trail

The HTTP-status verification for every URL in this file was run on 2026-05-27 from `compute-ocv-1`. Re-run it with this one-liner before trusting the file if it's > 30 days old:

```bash
for url in $(grep -oE 'https?://[^ )]+' references/coding-wikis-troubleshooting.md | sort -u); do
  printf "%s %s\n" "$(curl -s -L -o /dev/null -w '%{http_code}' -A 'Mozilla/5.0' --max-time 10 "$url")" "$url"
done
```

Any URL not returning 200 should be marked broken or replaced in the next session.
