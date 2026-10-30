# Tips Registry — the freshness ledger

> One row per published tip. **Any session that updates the site MUST walk this table first**
> (the rule lives in AGENTS.md). Dates here drive the pills on the page.

| ID | Tip | Depends on | How to verify | Added | Last verified/updated | Status |
|----|-----|-----------|---------------|-------|----------------------|--------|
| P1 | Subagent-driven builds | superpowers plugin (writing-plans, subagent-driven-development skills) | Plugin still installable; skills still named this | 2026-08-07 | 2026-08-19 | current |
| P2 | Self-naming tabs | `statusLine` settings block; `examples/statusline.sh` in starter kit repo (public); `jq` | Docs /en/statusline; kit repo reachable + file exists; `/plugin update kit` works | 2026-08-07 | 2026-08-19 | current |
| P3 | Turn work into skills | Skills system (`~/.claude/skills/[name]/SKILL.md`) | Docs /en/skills | 2026-08-07 | 2026-08-19 | current |
| P4 | The memory file | CLAUDE.md loading | Docs /en/memory | 2026-08-07 | 2026-08-19 | current |
| P5 | Resumable projects | Kit `/kit:scaffold-project`, project-conventions.md | Kit repo files exist; command ships | 2026-08-07 | 2026-08-19 | current |
| P6 | Plan mode | Shift+Tab mode cycle; `/plan` | Docs /en/permission-modes | 2026-08-07 | 2026-08-19 | current |
| P7 | Past sessions | Transcripts in `~/.claude/projects/`; `cleanupPeriodDays` (default 30) | Docs /en/settings; live machine (set to 120, 171 transcripts present 08-19) | 2026-08-07 | 2026-08-19 | current |
| P8 | Parallel sessions | Shared-surface pattern; git worktrees; kit multi-session primer | Kit primer exists (de-personalized 08-07); worktrees native git | 2026-08-07 | 2026-08-19 | current |
| P9 | Secrets | Password-manager runtime serving (1Password Environments); gitleaks | Kit 1password primer; gitleaks brew formula | 2026-08-07 | 2026-08-19 | current |
| P10 | Reversibility | CLAUDE.md standing rules; kit backup-before-edit + safety-net hooks | Kit hooks ship + wired in hooks.json | 2026-08-07 | 2026-08-19 | current |
| P11 | Scoped texts (Contacts group as allowlist) | macOS Contacts.app groups; chat.db readable w/ Full Disk Access; kit `docs/scoped-imessage-access-primer.md` | Kit primer exists; pattern re-verified against a live build (26/3,425 scope test, 2026-08-19) | 2026-08-19 | 2026-08-19 | current |
| P12 | Long sessions (four habits) | `/clear`, `/rename`, `/resume`, `/context`, `/mcp`, `/model`, `/compact <focus>`, `/rewind`; "Compact instructions" section in CLAUDE.md | Docs /en/costs + /en/prompt-caching (all commands and the cache behavior read 2026-10-10); kit `docs/context-budget-primer.md` exists | 2026-10-10 | 2026-10-10 | current |
| P13 | Meeting recordings (connector) | claude.ai Customize > Connectors; a recorder/notes app that offers a Claude connector; `/mcp` in Claude Code | Kit `docs/choosing-plugins-and-connectors-primer.md` exists; connector menu path matches kit Plaud primer (2026-10-10); recheck menu wording if claude.ai UI changes | 2026-10-10 | 2026-10-10 | current |
| P14 | Morning brief | Calendar + Gmail connectors; `/schedule`; slash commands/skills | Kit `docs/automation-recipes/01-morning-brief.md` exists; `/schedule` listed as a skill in current CC (2026-10-10) | 2026-10-10 | 2026-10-10 | current |
| P15 | Next actions on the calendar | Calendar connector; CLAUDE.md standing rule | Kit `docs/calendar-handoff-primer.md` exists | 2026-10-10 | 2026-10-10 | current |
| P16 | Catch-up briefs | Kit skill `bring-up-to-speed` | Kit `skills/bring-up-to-speed/SKILL.md` exists on main | 2026-10-10 | 2026-10-10 | current |
| P17 | Fireflies + Wispr Flow connectors (emailed 2026-08-07) | claude.ai Customize > Connectors listing for Fireflies and Wispr Flow | Menu path matches P13 (2026-10-10); fireflies.ai + wisprflow.ai 200 (2026-10-14); recheck that both still appear in the connector directory | 2026-10-14 | 2026-10-14 | current |
| P18 | All Google accounts in one Claude Code (emailed 2026-09-08) | Public repo `marianasmall/mariana-google-mcp` + its `SETUP-PROMPT.md`; Google Drive for desktop | Raw SETUP-PROMPT.md 200 and repo public (2026-10-14); prompt still covers the publish-to-production step | 2026-10-14 | 2026-10-14 | current |
| P19 | Free workshops and meetups (emailed 2026-10-11) | anthropic.com/events/build-with-claude; luma.com/claudecommunity | Both URLs 200 (2026-10-14); card names no dates on purpose, so only the pages and workshop names can go stale | 2026-10-14 | 2026-10-14 | current |

**Bench (candidates not yet published):** "AI reports are claims to verify" (needs a paste-able form) · a "five native features you're missing" roundup (/recap, Esc, @file, Ctrl+R, /usage) · to publish: join the Claude Duet waitlist, sent 2026-10-28.
| 01 | Spinner verbs | `spinnerVerbs` settings key | Live test on current CC (docs table omits it — verify by machine, not docs) | 2026-04 | 2026-08-19 (registry walk; see FRESHNESS-2026-08-19.md) | current |
| 02 | Spinner tips | `spinnerTipsOverride` settings key | UNDOCUMENTED in current docs (only `spinnerTipsEnabled` appears). Needs live interactive test | 2026-04 | — | **unverified — test next session** |
| 03 | Status line / mascot | `statusLine` block, script on stdin | Docs /en/statusline | 2026-04 | 2026-08-19 | current |
| 04 | Output styles | `/config` → Output style; `outputStyle` setting; frontmatter | Docs /en/output-styles (`/output-style` cmd REMOVED v2.1.91) | 2026-04 | 2026-08-19 | current |
| 05 | Sounds | Stop/Notification hooks | Docs /en/hooks | 2026-04 | 2026-08-19 | current |
| 06 | Themes | `/config theme=...` (v2.1.182+); `theme` setting | Docs /en/commands (`/theme` cmd GONE) | 2026-04 | 2026-08-19 | current |
| 07 | Slash commands | `.claude/commands/*.md` (merged into skills; still work) | Docs /en/skills merge note | 2026-04 | 2026-08-19 | current |

**Verification method (non-negotiable, learned 2026-08-07):** an AI freshness report is a
SECONDARY source. Before editing the site from one, reconcile every claimed deprecation against
(1) live machine state (`~/.claude/settings.json`, `claude --version`, does it actually run?) and
(2) official docs at code.claude.com. On 2026-08-07 an agent report claimed 5 of 7 tips broken;
only 3 needed changes, and 2 "deprecated" verdicts were flat wrong against the live machine.
Full reconciliation: `FRESHNESS-2026-08-07.md`.
