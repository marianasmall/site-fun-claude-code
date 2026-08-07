---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Custom Spinner Tips

<p class="tagline">The little hint that appears below the spinner. Turn it into a pep talk, a running joke, or a reminder to yourself.</p>

## What it does

Underneath the spinner verb, Claude Code shows a tip — usually a helpful note like "Try `/help` to see commands." You can replace that whole list with your own messages. Anything from motivation to inside jokes to reminders.

## Why it's fun

It's personality in a place most people never think to look. Mid-thought, your own voice shows up. Friends spot it over your shoulder and ask "…wait, did Claude just say that?"

## How to set it up

1. Open `~/.claude/settings.json`
2. Add the `spinnerTipsOverride` block below
3. Save. Next time Claude thinks, you'll see your tips

## Copy-paste starter

```json
{
  "spinnerTipsOverride": {
    "tips": [
      "This is fine.",
      "Trust the process.",
      "You got this.",
      "Small moves, smart moves.",
      "Shipping beats perfect.",
      "No pressure."
    ],
    "excludeDefault": false
  }
}
```

**`excludeDefault`** has two options:
- `false` — mix your tips with Claude's built-in ones *(recommended to start)*
- `true` — only show your tips, nothing else

## Fun ideas to try

- **Pep talk:** "You've done harder things than this", "One step is enough", "This is the good part"
- **Running jokes:** "Rod was right", "Tell Mom you're fine", "It's probably not DNS"
- **Reminders:** "Did you drink water?", "Stand up and stretch", "Check the slack"
- **Philosophy:** "Walk before you fly", "Naming is the hardest part", "The work is the reward"
- **Brand:** "Built with Claude Code", "Made in Santa Monica", "64 countries and counting"

## Shortcut: let Claude.ai write it for you

Paste this into [Claude.ai](https://claude.ai) with a theme you want:

> Give me 12 Claude Code spinner tips with the theme **[YOUR THEME]**. Each under 60 characters. Return in this exact JSON format for `~/.claude/settings.json`:
>
> ```
> {
>   "spinnerTipsOverride": {
>     "tips": ["...", "..."],
>     "excludeDefault": false
>   }
> }
> ```

**Themes that work well:**

- Pep talk for ADHD brains
- Reminders a parent would give you
- Motivational quotes from your favorite author
- Zen koans / short philosophy
- Inside jokes with your team

## Heads up

Tips are shown below the spinner verb, so keep them readable at a glance — under about 60 characters works best. Long tips get truncated or wrap awkwardly.

---

Docs: [code.claude.com/docs/en/settings](https://code.claude.com/docs/en/settings) — one of 7 in the Fun Claude Code series
