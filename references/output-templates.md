# Output Templates

Use the shortest template that still fits the task. Findings come first in every mode.

## Shared rules

- Findings first
- When there are multiple findings, order them by issue priority and decision impact
- Evidence second
- Assumptions or uncertainty third
- Omit sections that do not apply
- Do not emit empty headings or checklist filler
- Prefer normal markdown sections/lists for final output, even in Codex App
- Keep priority visible in the lead label of each finding or result row, for example `[P1]`
- Do not emit `::code-comment{...}` from this skill unless the user explicitly asks to force or test that format
- Render the final output as normal markdown sections/lists, not fenced code blocks, unless the user explicitly asked for a literal snippet
- If the task's explicit contract is comparative ranking or scoring, follow that contract and put the ordered result or score table first when the contract calls for it
- Use these templates as evidence-discipline guidance, not as a requirement to force ranking work into an audit-shaped report
- The anti-fabrication rule for rankings applies to candidate or artifact ordering, not to prioritizing findings within an audit
- If the required evidence bundle is missing, state that the task is blocked instead of inventing placeholder rankings or score tables

## Prior-output audit

Use for answers, plans, memos, reviews, and similar artifacts.

Rendered fallback shape:

Findings
- [P1] Material issue with impact and location

Evidence
- Local or external support for the finding

Assumptions / Uncertainty
- Only what remains unresolved

Delta
- Include only if a real baseline exists

## Claim verification

Use for fact-checking, freshness, and citation review.

Rendered fallback shape:

Findings
- [P1] Verified, contradicted, or unresolved claim summaries

Evidence
- Dated citations from primary sources

Unresolved Claims
- Only claims that could not be confirmed

Confidence / Uncertainty
- Residual ambiguity or stale-source risk

## System/change audit

Use for code, PRs, configs, runbooks, logs, and operational claims.

Rendered default shape:

Findings
- [P1] Material bug, regression, unsafe assumption, or operational risk

Evidence
- Files, tests, logs, repro steps, configs, or command output

Assumptions / Uncertainty
- Missing coverage or unresolved paths

Validation Steps
- Include only when recommending action

Rollback Steps
- Include only when tied to an operational decision or change recommendation

## Comparative ranking / scoring

Use when the task contract asks for blind ranking, comparative scoring, or rubric-driven ordering.

Rendered default shape:

Ordered Result / Score Table
- 1. [Top tier] Candidate or option, with brief rubric-aligned reason
- 2. [Second tier] Candidate or option, with brief rubric-aligned reason

Evidence / Rationale
- The load-bearing comparisons, contradictions, disqualifiers, or rubric deltas

Uncertainty / Missing Evidence
- Only what limits confidence or blocks a cleaner ranking

Blocked
- Include only when the required bundle is incomplete
