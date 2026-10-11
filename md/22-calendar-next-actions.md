---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Put What's Left on Your Calendar (P15)

<p class="tagline">A chat scrolls away. A calendar finds you. Added Oct 10, 2026.</p>

Connect your calendar, then paste this into Claude Code so it lands in your CLAUDE.md:

> Add this standing rule to my CLAUDE.md: "Schedule anything I need to do later. When we finish something and it ends with an action only I can take (an email to send, an approval, a decision, a login-gated edit), create a calendar event for it right then. Don't just tell me in chat. Every event description must include the exact steps, every link and file path I need, which account to sign in as, and why it matters. Never put a password in an event; say where it's stored. The test: I can act on that event alone, from my phone, weeks later. Check my calendar first for conflicts and duplicates, group related items into one slot, default to 15 minutes, and never send invitations to other people."

Or paste one line: "Read https://github.com/marianasmall/claude-code-starter-kit/blob/main/docs/calendar-handoff-primer.md and set this up for me." In claude.ai, the rule goes in your custom instructions.

**Caveat:** capturing each item as it happens is reliable. The end-of-session sweep is weak, because Claude can't detect that a session is ending; hook it to a wrap-up command or phrase you actually use.

**Test it:** end a real session with something waiting on you, then open the event on your phone. If you can't act on it from there, tell Claude what was missing.

Full primer: github.com/marianasmall/claude-code-starter-kit (docs/calendar-handoff-primer.md)
