---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Subagent-Driven Builds (P1)

<p class="tagline">The two-step for big builds: ask for a plan, then let fresh sub-agents execute it while the smartest model orchestrates and checks. Added Aug 7, 2026.</p>

## What it does

For any substantial build (3+ files, multiple decisions, more than 30 minutes of focused work), don't just ask for the thing. Paste this instead:

> **"Write an implementation plan, then execute it subagent-driven."**

Claude first writes a detailed implementation plan — every task with exact files, values, and test steps — then executes it by dispatching a FRESH sub-agent per task. Each one gets a written brief, builds, and self-reviews; then a separate reviewer agent (who never saw the work happen) adversarially checks it before the next task starts. The main session only coordinates — it never writes or reviews code itself. Fresh eyes catch what the author can't.

## Why it's powerful

- **Quality:** an independent reviewer per task catches what the builder can't see.
- **Cost:** the smartest model plans and checks; cheaper, faster agents do the labor.
- **Scale:** best for bigger projects — dashboards, websites, anything complex.

## Prerequisite

The **superpowers** plugin must be installed in Claude Code (it provides the writing-plans and subagent-driven-development skills). If it's not installed, ask Claude Code to install the superpowers plugin first.

## Optional upgrade

Tell Claude: *"Make this the standing default for big builds"* — it adds the rule to your CLAUDE.md so you never have to remember the phrase. Opt out per build with "quick and dirty, inline."
