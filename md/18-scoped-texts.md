---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Scoped texts (P11)

<p class="tagline">Give Claude your work texts (and nothing else). Added Aug 19, 2026. Carried by the starter kit.</p>

Claude gets much more useful when it can see real context — the thread where a delivery date was confirmed, the text with the address you need. But "let AI read my texts" has always meant all of them: family, doctors, everything. The fix: a group in your Mac's Contacts app becomes the permission. Whoever is in the group is visible to Claude; everyone else doesn't exist.

**First, put your work contacts in one place:** in Contacts.app, File > New Group, drag your work people in. (Contacts shows your iCloud and Google contacts together, so one group covers both.)

**Then paste:**

> Build a read-only iMessage reader. Derive the allowlist from my [group name] group in Contacts, and build it so it cannot return anything outside that list. Work from a copy of the message database — the live one is locked while Messages is open. No send capability in the code at all. Include a self-test.

**Then verify — this step is not optional.** Ask for a work thread (it should come back), then ask for a real personal contact (it should come back empty). A test only proves what it was written to prove, so use a real personal contact, not a made-up one.

**Why the wording matters:** the Mac can't do this scoping for you — its permission for reading Messages is all or nothing. The scoping lives in how the reader is built, which is why "cannot return anything outside that list" is the load-bearing phrase.

**The payoff:** on the machine this pattern came from, Claude sees 26 of 3,425 conversations — the work ones. Granting or revoking access is adding or removing someone in Contacts. Nothing else.

Full walkthrough (including the traps a real build hit): the kit's `docs/scoped-imessage-access-primer.md`.
