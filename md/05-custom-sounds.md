---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Custom Sounds

<p class="tagline">Make Claude chime when it's done. Different sound for "waiting on your approval." Never miss a turn again.</p>

## What it does

Claude Code can run a shell command at specific events — like when it finishes a turn, or when it's waiting for you to approve a permission. You can wire those events to play macOS system sounds, so you know what's happening without watching the terminal.

## Why it's fun

If you run long tasks, you can walk away and come back when you hear the chime. Different sounds for different events means you instantly know whether Claude finished — or is stuck waiting for you.

## How to set it up

1. Open `~/.claude/settings.json`
2. Add the `hooks` block below (merge with any existing `hooks` section)
3. Save. Next turn, you'll hear it

## Copy-paste starter

```json
{
  "hooks": {
    "Stop": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "afplay /System/Library/Sounds/Glass.aiff"
          }
        ]
      }
    ],
    "Notification": [
      {
        "hooks": [
          {
            "type": "command",
            "command": "afplay /System/Library/Sounds/Submarine.aiff"
          }
        ]
      }
    ]
  }
}
```

**`Stop`** fires when Claude finishes a turn. **`Notification`** fires when Claude is idle or waiting for your input.

## Built-in macOS sounds to pick from

All live in `/System/Library/Sounds/` — just swap the filename in the command:

| Sound | Vibe |
|-------|------|
| `Glass.aiff` | Clean bell — classic "done" sound |
| `Submarine.aiff` | Deep sonar ping — good for attention |
| `Ping.aiff` | Short, unobtrusive |
| `Pop.aiff` | Bubble pop — playful |
| `Purr.aiff` | Soft and warm |
| `Sosumi.aiff` | Quirky classic Mac sound |
| `Tink.aiff` | Light metallic — very quiet |
| `Blow.aiff` | Whoosh — surprising |
| `Funk.aiff` | Retro system chime |

Preview any of them from Terminal: `afplay /System/Library/Sounds/Glass.aiff`

## Fun ideas to try

- Different sounds for different events, so you hear without looking
- Use a long clip for big deploys: `afplay ~/Music/victory.mp3`
- Pair with a notification: add `osascript -e 'display notification "Done" with title "Claude"'` to the same hook
- Silent mode when you're in meetings: swap all sounds for empty strings

## Heads up

Hooks run every time the event fires, including short turns. If you're in a rapid-fire back-and-forth, a loud sound every 20 seconds gets old fast. Pick quiet sounds (`Tink.aiff`, `Pop.aiff`) for frequent events, and save the dramatic ones for `Notification`.

---

Docs: [code.claude.com/docs/en/hooks](https://code.claude.com/docs/en/hooks) — one of 7 in the Fun Claude Code series
