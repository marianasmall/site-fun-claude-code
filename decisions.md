# Decisions log

## 2026-08-07 — Rebrand + freshness system (session with Claude Code)
- **Rebranded** "Fun Things in Claude Code" → **"Mariana's Claude Code Tips"**, two chapters
  (Make it powerful / Make it fun). Old anchor ids kept stable — shared links keep working.
- **Every tip is dated** (Added / Updated / verified pills) — Mariana's call: readers must always
  know what's current.
- **Two-surface model:** Netlify = read, starter-kit repo = execute. Tips badge as
  "Paste-and-go" vs "In the starter kit" (kit owners just `/plugin update kit`).
- **Freshness rule + TIPS-REGISTRY.md** created: updates must re-verify listed tips against
  primary sources first. Born from an agent report that overclaimed deprecations
  (see FRESHNESS-2026-08-07.md).
- **Repo initialized** as `site-fun-claude-code` (public) — was an untracked folder deploying to
  Netlify with no version control.
- Content corrections shipped same day: `/output-style` → `/config` (removed v2.1.91),
  `/theme` → `/config theme=...`, slash-commands→skills merge note, added P3 (turn work into
  skills), plain-language pass on power chapter.

## 2026-04-17 — Original build (pre-repo)
- Seven fun customizations, single-page site, warm editorial design. Deployed to Netlify.
