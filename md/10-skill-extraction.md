---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Turn Work Into Skills (P3)

<p class="tagline">Never explain the same job twice. A skill is a saved procedure Claude keeps on file — and Claude can write it for you from work you just finished. Added Aug 7, 2026.</p>

## What it does

Done the same kind of task with Claude two or three times? Don't keep re-explaining it. Right after finishing a job you'll do again, paste:

> Turn what we just did into a reusable skill: capture the steps, the checks, and the gotchas we hit, so next time I can just ask for it by name.

Claude drafts a skill file from the work you just did together; you approve it. Next time, just ask for the job by name — Claude already knows every step.

## The ladder

- A prompt you repeat word-for-word → **slash command** (tip 07)
- A whole procedure you repeat — steps, checks, judgment calls → **skill**

Claude uses a skill automatically when the job matches, or you call it by name.

## How to know it's skill-worthy

- You've done it two or three times
- It has steps you'd forget
- You keep correcting Claude the same way each time — that correction is exactly what belongs in the skill

## Where skills live

`~/.claude/skills/[name]/SKILL.md` — plain markdown with a name, a description, and the steps. You never have to write it by hand.
