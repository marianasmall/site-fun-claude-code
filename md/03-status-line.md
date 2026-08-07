---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Custom Status Line (Your Mascot)

<p class="tagline">The bar at the bottom of Claude Code. Put an emoji, your name, the time, or a full dashboard with git branch and model name.</p>

## What it does

The status line is a thin bar that sits at the bottom of Claude Code at all times. You can set it to static text (a mascot emoji, a motto) — or to a shell script that updates every few seconds with live info like your current git branch, model name, cost, or time of day.

## Why it's fun

It's the one spot that's always visible. Everyone who sees your terminal sees it. It's the closest thing Claude Code has to a "home screen" — and you can make it yours.

## How to set it up — Level 1 (simple emoji)

1. Open `~/.claude/settings.json`
2. Add the `statusLine` block below
3. Save. It shows up immediately at the bottom.

## Copy-paste starter — simple mascot

```json
{
  "statusLine": {
    "type": "text",
    "text": "🤖 Claude Code — let's build"
  }
}
```

That's it. Replace the emoji and text with anything you want.

## Level 2 — dynamic script

If you want live info (git branch, time of day, model), point to a shell script instead:

```json
{
  "statusLine": {
    "type": "command",
    "command": "~/.claude/statusline.sh",
    "refreshInterval": 10
  }
}
```

Create `~/.claude/statusline.sh`:

```bash
#!/bin/bash
BRANCH=$(git rev-parse --abbrev-ref HEAD 2>/dev/null || echo "—")
HOUR=$(date +%H)
if [ $HOUR -lt 12 ]; then MOOD="☀️ Morning"; else MOOD="🌙 Evening"; fi
echo "$MOOD  🌳 $BRANCH"
```

Then make it executable: `chmod +x ~/.claude/statusline.sh`

## Fun ideas to try

- **Mascot:** `"🦄 You're a unicorn"` or `"🐙 Built by Mariana"`
- **Motto:** `"✨ Ship it ✨"` or `"Walk before you fly"`
- **Current state:** time of day, weather icon, mood emoji
- **Project-aware:** show current project name, client name, or focus area
- **Progress tracker:** word count of an active draft, PRs open, tests passing

## Shortcut: let Claude.ai write the script

Don't know bash? Describe what you want in [Claude.ai](https://claude.ai):

> Write me a bash script for Claude Code's `statusLine` command that shows **[WHAT YOU WANT]**. Return the full script ready to save as `~/.claude/statusline.sh`, plus the `chmod` step to make it executable and the JSON snippet for `settings.json`.

**Examples to describe:**

- "Current git branch, current time, and a rocket emoji"
- "The name of the project folder I'm in and today's date"
- "A motivational quote that changes every time it refreshes"
- "Whether my internet is working (ping google.com) plus battery percentage"

Claude.ai will write the bash for you — you just save it and run `chmod +x`.

## Heads up

If you use a shell script, keep it fast — it runs every few seconds. No API calls, no slow git commands, no network waits. Cache anything that doesn't change often.

---

Docs: [code.claude.com/docs/en/statusline](https://code.claude.com/docs/en/statusline) — one of 7 in the Fun Claude Code series
