---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Custom Spinner Verbs

<p class="tagline">Make Claude show a custom action word while it thinks. "Pondering…" "Scheming…" "Caffeinating…" — your call.</p>

## What it does

Every time Claude Code is thinking, a spinner shows an action word — by default "Thinking…" or "Pondering…". You can replace or extend that list with whatever you want. Each turn, Claude picks a random one from your list, so every response feels a little different.

## Why it's fun

It's the first thing you see every time Claude works, so tiny jokes land over and over again. Friends copy-paste your settings file to steal your best ones.

## How to set it up

1. Open the file `~/.claude/settings.json` (create it if it doesn't exist)
2. Add the `spinnerVerbs` block below — or merge it into your existing settings
3. Save. Changes show up on the next spinner — no restart needed

## Copy-paste starter

```json
{
  "spinnerVerbs": {
    "mode": "append",
    "verbs": [
      "Pondering",
      "Scheming",
      "Plotting",
      "Caffeinating",
      "Reading the room",
      "Not starting with 'Great question!'",
      "Pretending this is simple"
    ]
  }
}
```

**`mode`** has two options:
- `"append"` — keep Claude's built-in verbs, add yours to the mix *(recommended)*
- `"replace"` — only show your verbs, nothing else

## Fun ideas to try

- **Self-deprecating:** "Hallucinating (probably)", "Not ready to commit", "This could have been an email"
- **Character-based:** "Wondering what Boris would do", "Consulting the constitution", "Not being a tool (literally)"
- **Personal jokes:** "Checking if this is $20/hr work", "185 spinner verbs and counting"
- **Multi-language:** "Ci sto pensando", "Só um segundo", "Calibrando"
- **Reality check:** "Not hallucinating a citation", "Reading between your lines", "This is actually interesting"

## Shortcut: let Claude.ai write it for you

Don't want to brainstorm your own? Paste this prompt into [Claude.ai](https://claude.ai) and swap in a theme you love:

> Give me 15 Claude Code spinner verbs with the theme **[YOUR THEME]**. Return them in this exact JSON format, ready to drop into `~/.claude/settings.json`:
>
> ```
> {
>   "spinnerVerbs": {
>     "mode": "append",
>     "verbs": ["...", "..."]
>   }
> }
> ```

**Themes that generate great results:**

- ADHD humor ("Starting five things at once", "Waiting for deadline dopamine")
- Brazilian slang / Portuguese phrases ("Na boa", "Só um segundo", "Sem enrolação")
- Travel ("Upgrading (manifesting)", "Not eating at the airport")
- Your profession (marketing, law, parenting, wine)
- Pop culture (Taylor Swift lyrics, Star Wars, The Office)

Generate several batches with different themes, then merge them into one big list. That's how power users end up with 150+ spinner verbs.

## Heads up

If you set `"mode": "replace"` and only give 2-3 verbs, it gets repetitive fast. Aim for 10+ if you replace, or use `"append"` to blend with Claude's defaults.

---

Docs: [code.claude.com/docs/en/settings](https://code.claude.com/docs/en/settings) — one of 7 in the Fun Claude Code series
