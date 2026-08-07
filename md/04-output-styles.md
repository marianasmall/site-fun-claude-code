---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Output Styles

<p class="tagline">Change Claude's entire tone. Teacher mode. Pirate mode. Copywriter mode. Switch on the fly.</p>

## What it does

Output styles change how Claude writes — not what it does, but how it talks. There are three built-in styles, and you can write your own. Each one layers a personality on top of Claude's normal engineering smarts.

## Why it's fun

It's the fastest way to make Claude feel like a completely different collaborator. "Explanatory" mode adds teaching moments to every response. "Learning" mode asks you to fill in the code. Your custom style can make Claude a copywriter, a patient mentor, or a swashbuckling pirate.

## Built-in styles

| Style | What it does |
|-------|--------------|
| **Default** | Standard Claude Code — direct, efficient |
| **Explanatory** | Adds teaching insights to every response |
| **Learning** | Claude writes most of the code; leaves pieces for you to complete |

Switch via the `/output-style` command inside Claude Code, or set permanently in `~/.claude/settings.json`:

```json
{
  "outputStyle": "Explanatory"
}
```

## How to make a custom style

1. Create the folder: `mkdir -p ~/.claude/output-styles`
2. Create a file like `~/.claude/output-styles/mentor.md`
3. Use the template below
4. Activate with `/output-style mentor` or add `"outputStyle": "mentor"` to settings

## Copy-paste starter — Mentor style

Save as `~/.claude/output-styles/mentor.md`:

```markdown
---
name: Mentor
description: Explains decisions and asks questions before acting
---

You are a patient coding mentor. Before making changes:

1. Explain what you're about to do and why
2. Ask if there's a detail I should consider
3. After the change, point out one thing I could learn from it

Never write more than one file without pausing to check in.
```

That's it — that's the whole file. Markdown with a short frontmatter block.

## Fun styles to try

- **Copywriter:** writes in punchy, benefit-first marketing copy
- **Analyst:** lists "what we know / assume / don't know / recommend" before every answer
- **Pirate:** translates all responses into pirate speak (yes, really)
- **Therapist:** asks reflective questions instead of solving immediately
- **Brutally honest friend:** no hedging, just the answer

## Shortcut: let Claude.ai write the style for you

Describe the persona and [Claude.ai](https://claude.ai) will generate the file:

> Write me a Claude Code output style that makes Claude respond like **[PERSONA]**. Return it as a complete markdown file with frontmatter, ready to save as `~/.claude/output-styles/[name].md`. Keep it to 6-10 lines of actual instructions.

**Personas that produce distinct styles:**

- A patient mentor who explains the "why" behind every decision
- A no-BS startup advisor who challenges assumptions
- A copywriter who makes every sentence punchy
- A kindergarten teacher explaining to a 5-year-old
- A marketing strategist obsessed with the audience's jobs-to-be-done

Save the file Claude.ai returns. Activate with `/output-style [name]`.

## Heads up

Output styles kick in on new sessions — if you change style mid-conversation, run `/clear` or start a new session to see the new tone. Your coding skills stay intact either way.

---

Docs: [code.claude.com/docs/en/output-styles](https://code.claude.com/docs/en/output-styles) — one of 7 in the Fun Claude Code series
