---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Parallel Sessions (P8)

<p class="tagline">Run several Claudes as a team — colleagues, not clones. Added Aug 7, 2026. Carried by the starter kit.</p>

**Paste:**

> I want to run multiple Claude Code sessions in parallel without them stepping on each other. Set me up: what files should they share, how does one session hand work to another, and what habits keep them coordinated?

**The three rules:** shared files beat memory (sessions coordinate through what's written down) · update the handoff on state change, not just at session end · when work moves to a new session, the old one writes the new one's first message.

**Same repo, two sessions?** Git worktrees give each session its own copy on its own branch — same history, separate desks. Ask: *"set up a worktree so I can work on [thing] in a second session without touching this one."*

Kit users have the pieces: self-naming tabs (P2), `/kit:handoff`, `/kit:session-end`, and the full primer in the kit's `docs/multi-session-coordination-primer.md`.
