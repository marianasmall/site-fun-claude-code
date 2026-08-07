# AGENTS.md — site-fun-claude-code

## What this is
Mariana's public Claude Code tips site: **https://fun-claude-code.netlify.app**
("Mariana's Claude Code Tips — make it fun, make it powerful"). A living, dated collection.
Two chapters: **Make it powerful** (P1, P2, P3…) and **Make it fun** (01–07).

## Where things live
- `site/index.html` — the ENTIRE site (single self-contained file, inline CSS). Deployed to Netlify.
- `md/NN-*.md` — per-tip source/PDF versions (historical for 01–07; keep in sync on content changes).
- `TIPS-REGISTRY.md` — one row per tip: dependency, verify method, dates. **Drives the date pills.**
- `FRESHNESS-*.md` — dated verification reconciliation logs.
- `_backups/` folders — hook-generated, gitignored.

## THE FRESHNESS RULE (why this repo has a registry)
Before ANY content update to the site:
1. Walk `TIPS-REGISTRY.md` and re-verify each listed tip against **primary sources**:
   live machine state (settings.json keys, `claude --version`, does it actually run?) and
   official docs (code.claude.com/docs). A claude-code-guide agent may draft the check, but its
   report is SECONDARY — reconcile before editing. (2026-08-07: an agent called 5/7 tips broken;
   only 3 needed changes.)
2. Update date pills: `Added <date>` (new) · `Updated <date>` (content changed) ·
   `<added> · verified <date>` (checked, still current).
3. Bump the hero "Last updated" date, registry rows, and the matching `md/` file.
4. Mechanical QA before deploy: unique IDs, copy-btn targets resolve, anchors resolve, tag balance.
5. Deploy: `netlify deploy --dir .` (draft, from `site/`), visual check, then `--prod`.

## Companion repo
`github.com/marianasmall/claude-code-starter-kit` (PUBLIC) — the "execute" surface.
The site is the "read" surface. Kit-carried tips (P2) badge as "In the starter kit" and offer
`/plugin update kit`; paste-a-phrase tips badge "Paste-and-go". New file-based tips should land
in the kit AND get a site section.

## Conventions
- Every tip: section-grid pattern (section-head w/ terminal preview + section-body w/ shortcut
  card + details expander). Clone an existing section; don't invent new patterns.
- Date pill + path badge on every section-num line.
- Newcomer-friendly language: gloss jargon on first use ("sub-agents" = helper Claudes,
  CLAUDE.md = Claude's memory file). The reader is a smart friend who does NOT live in Claude Code.
- Keep existing anchor ids stable — links are in the wild.
- Voice: warm, direct, Mariana's share-with-friends tone. Emojis sparingly.

## Gotchas
- `.section:nth-child(even)` alternation counts ALL children of `<main>` — chapter-head divs
  shift parity. Check adjacent-section contrast after inserting sections.
- `md/` front-matter expects `../style.css` (PDF pipeline; optional).
- The old `/theme` and `/output-style` mentions on the page are INTENTIONAL historical notes.
