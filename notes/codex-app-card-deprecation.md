# Codex App review-card deprecation note

Status: temporary local policy for `woz-audit` as of 2026-03-15.

This note is intentionally not linked from `SKILL.md` so it does not auto-load with the skill. It exists as a repo-local record of why `woz-audit` stopped recommending `::code-comment{...}` cards as a normal output format.

## Why cards are deprecated in `woz-audit`

- Card emission creates sticky review state in Codex App rather than acting like a neutral pretty-printer.
- Dismissing a card in the UI did not appear to durably suppress it across subsequent prompting in the same thread.
- Prior card state can come back as a `Review findings` block in later prompts, which changes prompt contents and consumes tokens.
- That behavior is tolerable for true interactive review workflows, but it is a poor default for audits, rankings, and verification passes that mainly want readable output.

## Current-client behavior observed during local probes

- `::code-comment` requires a `file` field to render as a card in the tested client behavior.
- A nonce file path can still render a card, which is another reason not to treat cards as harmless formatting.
- Rich formatting and links rendered in the card body during local tests.
- Formatting and links should not be relied on in the card title.
- UI affordances such as finding counts and `Add` / `Dismiss` are client-driven, not prompt-controlled.

## Revisit condition

Revisit card usage only when the client offers a less sticky or more flexible review-card mode, or when a task explicitly calls for real interactive review findings despite the current UX tradeoffs.
