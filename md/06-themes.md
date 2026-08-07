---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Themes

<p class="tagline">Change the colors. Light, dark, auto-switch, or colorblind-friendly. The fastest customization on this list.</p>

## What it does

Claude Code has its own color palette, separate from your terminal. You pick the theme and it changes immediately — no restart, no file editing. Good for matching your mood, your room's lighting, or an accessibility need.

## Why it's fun

It's the easiest one. Takes five seconds. Completely changes the feel of the interface.

## How to set it up

**Option 1: Interactive** — type `/theme` inside Claude Code and pick from a menu.

**Option 2: Permanent** — add this to `~/.claude/settings.json`:

```json
{
  "theme": "dark"
}
```

## All theme options

| Theme | When to use it |
|-------|----------------|
| `"auto"` | Follows your macOS system setting (dark at night, light by day) |
| `"dark"` | Classic dark mode — default for most people |
| `"light"` | High-contrast light — great for daylight, projectors, screenshots |
| `"dark-daltonized"` | Dark + colorblind-friendly (for red-green color differences) |
| `"light-daltonized"` | Light + colorblind-friendly |
| `"dark-ansi"` | Dark using your terminal's ANSI colors (match your terminal theme) |
| `"light-ansi"` | Light using your terminal's ANSI colors |

## Fun ideas to try

- **`auto`** — lets your environment decide; feels like Claude is paying attention
- **`light`** for recording videos or taking screenshots — dark themes photograph poorly
- **`dark-daltonized`** if you've ever struggled to tell green from red in test output
- **`dark-ansi`** if you already love your terminal theme and want Claude to match

## Heads up

Themes change instantly — no restart needed. If you can't read something, just run `/theme light` (or `/theme dark`) and it switches on the spot.

---

Docs: [code.claude.com/docs/en/commands](https://code.claude.com/docs/en/commands) — one of 7 in the Fun Claude Code series
