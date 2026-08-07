# Freshness Verification — 2026-08-07

Method: claude-code-guide agent report (SECONDARY) reconciled against primary sources:
live machine state (CC 2.1.224, ~/.claude/settings.json) + official docs (code.claude.com).

| Tip | Agent verdict | Primary-source verdict | Action |
|-----|--------------|------------------------|--------|
| 01 spinnerVerbs | DEPRECATED (claimed removed 2.1.206+) | **WORKS on 2.1.224** — live config has 185 verbs, in daily use. Settings docs table doesn't list it (docs gap or fetch miss). | KEEP. Pending: targeted docs probe for "spinner" keys. |
| 02 spinnerTips | DEPRECATED | Docs mention `spinnerTipsEnabled` (feature family exists). Key name used on site needs checking vs docs. | VERIFY key name; keep unless disproven. |
| 03 statusLine | "REWRITE completely" | **WRONG.** Docs: script via `statusLine` block, JSON on stdin — exactly what site teaches and what live config (`type:"command"`) runs (rebuilt today). | KEEP. Sanity-check site snippet shape. |
| 04 output styles | `/output-style` removed v2.1.91 | **CONFIRMED by docs verbatim** ("deprecated in v2.1.73 and removed in v2.1.91. Use /config or edit outputStyle"). Built-ins now: Default + Proactive/Explanatory/Learning. | FIX site section: /config path, styles list, `keep-coding-instructions` frontmatter. |
| 05 sounds/hooks | CURRENT | Hooks docs valid; Stop/Notification unchanged. | No change. |
| 06 /theme | Not a command; use /config | Plausible (CC now routes theme via /config). | VERIFY against /docs/en/commands before editing. |
| 07 slash commands | "Merged into Skills; legacy" | Docs: "Custom commands have been merged into skills… Your existing .claude/commands/ files keep working." Same /name invocation. | MINOR: add one-line note; content stays. |
| /plugin update | `/plugin update [name]` current | Confirmed. | Use `/plugin update kit` in P2 kit-note. |
| docs/en/plugins URL | valid | Confirmed valid (P1 docs link OK). | No change. |

Lesson (for the registry rule): peer-AI freshness reports MUST be reconciled against
live machine state + official docs before edits. This agent was right on 2 of 7,
overclaimed deprecation on at least 2 others.
