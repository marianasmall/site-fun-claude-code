# Tips Registry — the freshness ledger

> One row per published tip. **Any session that updates the site MUST walk this table first**
> (the rule lives in AGENTS.md). Dates here drive the pills on the page.

| ID | Tip | Depends on | How to verify | Added | Last verified/updated | Status |
|----|-----|-----------|---------------|-------|----------------------|--------|
| P1 | Subagent-driven builds | superpowers plugin (writing-plans, subagent-driven-development skills) | Plugin still installable; skills still named this | 2026-08-07 | 2026-08-07 | current |
| P2 | Self-naming tabs | `statusLine` settings block; `examples/statusline.sh` in starter kit repo (public); `jq` | Docs /en/statusline; kit repo reachable + file exists; `/plugin update kit` works | 2026-08-07 | 2026-08-07 | current |
| P3 | Turn work into skills | Skills system (`~/.claude/skills/[name]/SKILL.md`) | Docs /en/skills | 2026-08-07 | 2026-08-07 | current |
| 01 | Spinner verbs | `spinnerVerbs` settings key | Live test on current CC (docs table omits it — verify by machine, not docs) | 2026-04 | 2026-08-07 (live: works on 2.1.224) | current |
| 02 | Spinner tips | `spinnerTipsOverride` settings key | UNDOCUMENTED in current docs (only `spinnerTipsEnabled` appears). Needs live interactive test | 2026-04 | — | **unverified — test next session** |
| 03 | Status line / mascot | `statusLine` block, script on stdin | Docs /en/statusline | 2026-04 | 2026-08-07 | current |
| 04 | Output styles | `/config` → Output style; `outputStyle` setting; frontmatter | Docs /en/output-styles (`/output-style` cmd REMOVED v2.1.91) | 2026-04 | 2026-08-07 (updated) | current |
| 05 | Sounds | Stop/Notification hooks | Docs /en/hooks | 2026-04 | 2026-08-07 | current |
| 06 | Themes | `/config theme=...` (v2.1.182+); `theme` setting | Docs /en/commands (`/theme` cmd GONE) | 2026-04 | 2026-08-07 (updated) | current |
| 07 | Slash commands | `.claude/commands/*.md` (merged into skills; still work) | Docs /en/skills merge note | 2026-04 | 2026-08-07 (updated) | current |

**Verification method (non-negotiable, learned 2026-08-07):** an AI freshness report is a
SECONDARY source. Before editing the site from one, reconcile every claimed deprecation against
(1) live machine state (`~/.claude/settings.json`, `claude --version`, does it actually run?) and
(2) official docs at code.claude.com. On 2026-08-07 an agent report claimed 5 of 7 tips broken;
only 3 needed changes, and 2 "deprecated" verdicts were flat wrong against the live machine.
Full reconciliation: `FRESHNESS-2026-08-07.md`.
