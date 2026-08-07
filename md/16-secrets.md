---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Secrets (P9)

<p class="tagline">Get your API keys off your disk. Added Aug 7, 2026. Carried by the starter kit.</p>

A key pasted into a file sits in plaintext — readable by any process, one accidental commit from public. Your password manager can serve keys to Claude Code at runtime instead.

**Paste (note the last sentence — it matters):**

> Audit my Claude Code setup for secrets sitting in plaintext — settings.json, .env files, shell scripts. Tell me what you find and how to move each one into my password manager. Never print the actual secret values, only where they live.

A security audit that prints your keys into the chat has just copied them somewhere new.

**How it works:** 1Password's Environments feature (desktop app) serves keys through a secure pipe scripts read at runtime — nothing stored in files. **Belt and suspenders:** ask Claude to install `gitleaks`, a pre-commit scanner that blocks commits containing anything key-shaped.

Full walkthrough: the kit's `docs/1password-environments-primer.md`.
