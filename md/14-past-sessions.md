---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Past Sessions (P7)

<p class="tagline">Your old conversations aren't gone — Claude can go read them. Added Aug 7, 2026.</p>

Every Claude Code session is saved as a transcript file on your own machine (under `~/.claude/projects/`) — 30 days by default. Nothing leaves your computer.

**Paste:**

> Search my past Claude Code sessions for [TOPIC] and summarize what we did and what we decided.

**Keep them longer** — one line in `~/.claude/settings.json`:

```json
{ "cleanupPeriodDays": 120 }
```

Related built-ins: `/resume` reopens a past session; `/recap` summarizes one when you return. Kit users: `/kit:recall` is a ready-made version of the search.

Docs: code.claude.com/docs/en/settings (cleanupPeriodDays)
