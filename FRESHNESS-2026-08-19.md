# Freshness reconciliation — 2026-08-19

Occasion: adding P11 (scoped texts) triggered the mandatory registry walk (AGENTS.md rule).
Machine: Claude Code 2.1.236.

## Method

A subagent ran the full 17-tip verification (live machine state + code.claude.com docs +
starter-kit repo reachability via GitHub API). Its report was reconciled per the registry's
non-negotiable rule: the main session independently confirmed the machine-side claims
(settings.json keys spinnerVerbs/statusLine/cleanupPeriodDays present, jq, gitleaks 8.30.1,
kit files on disk, superpowers skills live in-session). The agent claimed ZERO deprecations,
so no docs-claim required adversarial re-checking — the risky class from 2026-08-07
(false "broken" verdicts) did not occur.

## Result

- **16 of 17 CURRENT.** Registry "Last verified" bumped to 2026-08-19 on those rows.
- **Tip 02 (spinnerTipsOverride): still CANNOT-VERIFY.** Key remains absent from
  /en/settings docs (only spinnerTipsEnabled appears, in a scope-precedence example) and
  from the live settings.json. Still needs a live interactive test. Status unchanged.
- **Tip 01 (spinnerVerbs): key present and populated on 2.1.236** ({mode: "append"});
  docs still omit the key, as the registry's verify note predicts. The registry's own method
  (interactive display test) was last performed on 2.1.224 — key presence + no deprecation
  evidence justified the CURRENT verdict; a display re-test remains nice-to-have.
- **P7 cosmetic**: transcript-count snapshot updated 175 → 171.
- **06 footnote**: docs mention /theme once as a fullscreen-rendering dialog command;
  does not contradict the tip (standalone /theme is gone from the commands table).

## Changes shipped alongside this pass

- P11 · Scoped texts added (site section, registry row, md/18-scoped-texts.md,
  kit primer docs/scoped-imessage-access-primer.md in the starter-kit repo).
- No content changes to existing tips; their site pills unchanged (month-level pills
  "verified Aug 2026" remain accurate).

Raw agent evidence: session scratchpad (freshness-findings-2026-08-19.md, ephemeral).
