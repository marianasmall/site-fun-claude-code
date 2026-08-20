---
css: ../style.css
pdf_options:
  format: Letter
  margin: 0.5in
  printBackground: true
---

# Scoped texts (P11)

<p class="tagline">Give Claude your work texts (and nothing else). Added Aug 19, 2026. Carried by the starter kit.</p>

Claude gets much more useful when it can see real context — the thread where a delivery date was confirmed, the text with the address you need. But "let AI read my texts" has always meant all of them: family, doctors, everything. The fix: a list in your contacts becomes the permission. Whoever is on the list is visible to Claude; everyone else doesn't exist.

**First, put your work contacts in one place:** a list in the Mac's Contacts app (File > New List — [Apple's how-to](https://support.apple.com/guide/contacts/create-and-change-lists-adrb3280fe91/mac); older Macs call it a group), or a [label in your work Google contacts](https://support.google.com/contacts/answer/30970). Contacts shows iCloud and Google side by side, so either works.

**Then paste:**

> Build an iMessage reader. Derive the allowlist from my [list/label name] contacts, and build it so it cannot return anything outside that list. It may draft replies by opening Messages prefilled, but no send capability may exist in the code. Work from a copy of the message database — the live one is locked while Messages is open. Include a self-test.

**Then verify — this step is not optional.** Ask for a work thread (it should come back), then ask for a real personal contact (it should come back empty). Have it draft to a fake number to prove nothing can deliver. A test only proves what it was written to prove, so use a real personal contact, not a made-up one.

**Why the wording matters:** the Mac can't do this scoping for you — its permission for reading Messages is all or nothing. The scoping lives in how the reader is built. The principle: make the scope structural, not a filter. Personal messages aren't filtered out of results — they're in data the tool never opens. There's no filter to get wrong.

**The one hard rule:** it never sends. Drafting is fine — it opens Messages with the reply loaded and you press send.

**Not on a Mac?** The texts part needs one — iMessage's database only exists on Apple devices. But the trick isn't Mac-only: the same work-contacts label can scope Claude's email or calendar reading instead. Same wording, same verification step.

**The payoff:** on the machine this pattern came from, Claude sees 26 of 3,425 conversations — the work ones. Granting or revoking access is adding or removing someone in Contacts. Nothing else.

Full walkthrough (including the traps a real build hit): the kit's `docs/scoped-imessage-access-primer.md`.
