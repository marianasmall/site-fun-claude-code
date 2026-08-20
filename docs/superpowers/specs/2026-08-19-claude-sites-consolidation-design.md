# Claude Sites Consolidation — Design Spec

**Date:** 2026-08-19 · **Status:** Approved by Mariana (verbal, same evening) · **Owner repo:** site-fun-claude-code (the hub owns the consolidation; Build 2 executes in ia-before-ai)

## Problem

Three public Netlify properties grew ad hoc around one purpose (help Mariana's friends understand Claude / Claude Code and set themselves up):

| Property | State at audit (2026-08-19) |
|---|---|
| fun-claude-code.netlify.app | Healthy. 18 dated tips, freshness registry, verified 08-19 (16/17 current). |
| anthropic-stack-preview.netlify.app | Stale + beta-labeled. 12,000-word teaching framework; last updated 04-28; cites Opus 4.7 as current; its own promised refresh cadence already broken. Repo: ia-before-ai. |
| claude-code-starter-kit.netlify.app | Superseded. Old React SPA ("For Marketing Executives"), last deploy 03-20, local repo literally archive-site-claude-starter-kit. Kit's real home: public GitHub repo (the "execute" surface, ratified 08-07). |

Root cause is not duplication of content — the properties serve three different reader states (new-to-AI / set-me-up / go-deep). The failures are (1) no front door routing by state and (2) no shared freshness system: the one site with a registry stayed true, the one without rotted.

## Decision (ratified answers)

- **Approach: hub-and-spokes.** Consolidate the front door and the freshness discipline, NOT the documents. (Alternatives rejected: true merge — breaks in-the-wild anchors, concentrates maintenance; index-page-only — keeps stale properties public, fails decay resistance.)
- **Stack framework: refresh + promote** (not date-stamp, not unpublish).
- **Domain: claude.marianasmall.ai** as custom domain on the hub; netlify.app URLs keep working (never rename the Netlify site — renaming frees the old name and breaks live links).
- **No full content rethink / relayout.** Ratified when asked directly: too much lift for the purpose. Included instead: a light IA pass on the page top only (hero + start-here band) at build time via information-architect skill. Full redesign only if the site's mission changes (e.g., course launch).

## Build 1 — Hub + retirement + domain (~1 hr, any session)

1. **Start-here band** at top of fun-claude-code index, three doors by reader state:
   - "New to AI or Claude entirely" → https://marianasmall.ai/where-to-start-with-ai (exists, current, personal-brand surface — the hub links it, never duplicates it)
   - "Ready to set up Claude Code" → Make-it-powerful chapter + starter kit (existing anchors)
   - "Want the deep mental model of the whole Anthropic ecosystem" → refreshed stack framework (link goes live with Build 2; band ships with the door present but pointing at current URL + "refresh in progress" pill until then — or ships after Build 2; builder's call)
   - Constraints: every existing anchor id stays stable; section-parity gotcha in AGENTS.md applies; newcomer voice (gloss jargon); date pill on the band like any tip.
2. **Retire starter-kit Netlify site**: replace deploy with a `_redirects` file — `/* → https://fun-claude-code.netlify.app/#h-resumable-projects 301` (target: the hub; exact anchor = builder verifies the kit-related section id at build time). Record in decisions.md both repos' side. Reversible by redeploying the archived repo.
3. **Domain**: attach claude.marianasmall.ai to the fun-claude-code Netlify site. First check where marianasmall.ai DNS is managed (Netlify DNS vs registrar); if registrar, Mariana adds one CNAME (exact record provided by builder). Then optionally update the where-to-start link (added 08-19) to the pretty URL — old URL keeps working either way.
4. **Registry**: add a registry row for the start-here band (depends on: where-to-start page live; stack framework URL; kit repo public).

## Build 2 — Stack framework refresh (~2–3 hrs, fresh session, in ia-before-ai)

- **Scope:** re-verify product-map/tool-name sections against current Anthropic docs (the rot: model names — Opus 4.7 → Claude 5 family/Opus 5/Fable — product lineup, feature names); light-touch evergreen sections (Transformation Arc, 8 dimensions — Mariana's IP, ages well); drop "Phase 1 Preview" label → v1.1; visible as-of date; add a FRESHNESS ledger to ia-before-ai modeled on TIPS-REGISTRY (per-section verify method + dates) so it cannot silently rot again.
- **Execution:** standing default — writing-plans → subagent-driven; parallel doc-verification agents (one per product-map section) so bulky doc fetches stay out of the main context. Reconcile agent reports against primary sources before editing (AI freshness reports are SECONDARY — see fun-claude-code FRESHNESS-2026-08-07 incident).
- **OPEN DECISION (Mariana's, at Build 2 start):** the original 04-17 plan gated public promotion on 2–3 beta readers. Waive, or run the beta gate now? Neither pre-decided.
- Post-ship ping list from the original project (Rui Vas credit/share) still applies.

## Freshness governance

- Hub: existing TIPS-REGISTRY discipline unchanged; band gets a row.
- Framework: new ledger in ia-before-ai; /maintain's monthly capability review should glance at both ledgers' oldest verified dates.

## Success criteria

- One URL a friend can be given (claude.marianasmall.ai) that routes all three reader states.
- Zero live pages claiming stale facts as current (framework refreshed; SPA retired).
- Every surviving public page governed by a freshness ledger.
- No existing in-the-wild link 404s (redirects + stable anchors).

## Non-goals

Full redesign or content rewrite of the tips; merging the framework into the hub; touching where-to-start-with-ai beyond the optional pretty-URL swap; any change to the GitHub starter-kit repo's role.
