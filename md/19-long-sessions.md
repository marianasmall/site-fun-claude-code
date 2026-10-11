---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Four Habits for Long Days (P12)

<p class="tagline">Keep long sessions fast and cheap. Added Oct 10, 2026.</p>

Claude re-reads the whole conversation every time you send a message, so a long one gets slow and uses more of your limit. Four habits keep it light:

1. **Starting something unrelated?** Type `/clear` (use `/rename` first if you want to `/resume` the old one later).
2. **Feeling slow?** Type `/context` to see what's taking room, then `/mcp` to switch off connected tools you aren't using.
3. **Pick your model at the start and stay on it.** Switching with `/model` mid-task makes the next reply slower.
4. **Before a break or between tasks, tell Claude what to keep:**

> /compact keep the decisions we made, the files we changed, and the open questions

Went down the wrong path? `/rewind` goes back to an earlier point.

**Write it once:** ask Claude to add a "Compact instructions" section to your CLAUDE.md so it knows what to keep when it compacts on its own.

Docs: code.claude.com/docs/en/costs and code.claude.com/docs/en/prompt-caching
