---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Custom Slash Commands

<p class="tagline">Build your own shortcuts. `/joke`, `/standup`, `/greet` — whatever you'd type often, turn it into one word.</p>

## What it does

Slash commands are shortcuts you invoke by typing `/name` in Claude Code. Each one is a markdown file with a prompt template. Claude reads the file and runs it as if you'd typed the full prompt. They can take arguments, run shell commands, and even call specific agents.

## Why it's fun

Once you have three or four of these, you feel like the interface is yours. The same way power users have bash aliases, power Claude Code users have slash commands. Everyone you show them to asks for the files.

## How to set it up

1. Create the folder: `mkdir -p ~/.claude/commands`
2. Create a file named after the command, e.g. `~/.claude/commands/joke.md`
3. Write a prompt in the file (see template below)
4. Type `/joke` in Claude Code — it runs

## Copy-paste starter — `/joke`

Save as `~/.claude/commands/joke.md`:

```markdown
---
description: Tell a joke about a topic
argument-hint: "[topic]"
---

Tell me a funny, clever joke about $ARGUMENTS. Aim for smart, not corny. One joke only.
```

Then in Claude Code, type: `/joke quantum computing`

## Fun commands to try

**`/standup`** — quick morning update:

```markdown
---
description: Generate a 30-second standup
---

Based on my recent work, write a 3-bullet standup:
- What shipped yesterday
- What's next today
- Any blockers
```

**`/pep`** — when you need encouragement:

```markdown
---
description: Motivational pep talk
---

Give me a 2-sentence pep talk. No corporate cheese. Be specific about why I can handle what's in front of me.
```

**`/brainstorm`** — structured idea generation:

```markdown
---
description: Generate 5 ideas with a constraint
argument-hint: "[topic] [constraint]"
---

Generate 5 creative ideas about $ARGUMENTS. Each should be one sentence, novel, and actionable this week.
```

**`/greet`** — start of session reset:

```markdown
---
description: Fresh session check-in
---

Good morning. Before we start: what's active in my world right now that I should reload into context? Ask me 2-3 questions to calibrate.
```

## Shortcut: let Claude.ai write the command

Describe the shortcut you want and [Claude.ai](https://claude.ai) will generate the file:

> Write me a Claude Code slash command called `/[NAME]` that does **[WHAT YOU WANT]**. Return it as a complete markdown file with frontmatter, ready to save as `~/.claude/commands/[name].md`. Keep the prompt clear and specific.

**Examples to ask for:**

- A `/recap` command that summarizes my last 3 Slack messages into one action
- A `/decide` command that helps me pick between two options using a pros/cons framework
- A `/elevator` command that turns a long idea into a 30-second elevator pitch
- A `/reframe` command that takes a negative thought and offers 3 alternative framings
- A `/translate` command that takes business-speak and turns it into plain English

Save the file. Type `/` in Claude Code to see it in the menu.

## Heads up

Slash commands live in two places:
- `~/.claude/commands/` — available in every project (personal)
- `./.claude/commands/` inside a project folder — only available in that project

Commands use the same Claude you're talking to now — they don't cost anything extra. They just save you from re-typing the prompt.

---

Docs: [code.claude.com/docs/en/slash-commands](https://code.claude.com/docs/en/slash-commands) — one of 7 in the Fun Claude Code series
