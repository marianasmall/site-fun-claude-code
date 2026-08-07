---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Self-Naming Terminal Tabs (P2)

<p class="tagline">Terminal tabs that name themselves after whatever each conversation is about — total sanity-saver if you run more than one session. Added Aug 7, 2026. Carried by the starter kit.</p>

## What it does

Each Claude Code session names its own terminal tab to match what it's working on. Run three sessions at once and every tab tells you which is which — automatically.

## Set it up (one paste)

Paste this into Claude Code and it installs itself:

> Set up the statusline from https://github.com/marianasmall/claude-code-starter-kit — copy examples/statusline.sh to ~/.claude/statusline.sh, make it executable, and wire the statusLine block into my ~/.claude/settings.json. Don't overwrite anything I already have; if I already have a statusline, show me what to merge.

Needs a reasonably current Claude Code and the `jq` tool.

## Or grab the whole starter kit

```
/plugin marketplace add https://github.com/marianasmall/claude-code-starter-kit
/plugin install kit@claude-code-starter-kit
```

Installing as a plugin means updates flow to you — when new tips land in the kit, update once from `/plugin` and you're current.

**Already installed the kit?** You have this — just update the plugin.

## Related

Fun tip 03 (mascot status line) lives in the same bar — the kit statusline and the mascot are cousins and can be merged.
