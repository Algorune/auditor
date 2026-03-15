# Output Templates

Use the shortest template that still fits the task. Findings come first in every mode.

## Shared rules

- Findings first
- When there are multiple findings, order them by issue priority and decision impact
- Evidence second
- Assumptions or uncertainty third
- Omit sections that do not apply
- Do not emit empty headings or checklist filler
- In Codex App code reviews with precise file locations, prefer `::code-comment{...}` directives for findings so priority renders natively
- In Codex App artifact-backed rankings, you may also use `::code-comment{...}` directives to render one card per ranked item
- When native app directives are unavailable, keep priority visible in the lead label of each finding or result row, for example `[P1]`
- If the task's explicit contract is comparative ranking or scoring, follow that contract and put the ordered result or score table first when the contract calls for it
- Use these templates as evidence-discipline guidance, not as a requirement to force ranking work into an audit-shaped report
- The anti-fabrication rule for rankings applies to candidate or artifact ordering, not to prioritizing findings within an audit
- If the required evidence bundle is missing, state that the task is blocked instead of inventing placeholder rankings or score tables

## Prior-output audit

Use for answers, plans, memos, reviews, and similar artifacts.

```md
Findings
- [P1] Material issue with impact and location

Evidence
- Local or external support for the finding

Assumptions / Uncertainty
- Only what remains unresolved

Delta
- Include only if a real baseline exists
```

## Claim verification

Use for fact-checking, freshness, and citation review.

```md
Findings
- [P1] Verified, contradicted, or unresolved claim summaries

Evidence
- Dated citations from primary sources

Unresolved Claims
- Only claims that could not be confirmed

Confidence / Uncertainty
- Residual ambiguity or stale-source risk
```

## System/change audit

Use for code, PRs, configs, runbooks, logs, and operational claims.

For Codex App code reviews with precise file/line locations, prefer one directive per finding:

```text
::code-comment{title="[P1] Short finding label" body="One-paragraph explanation of the bug or risk, with impact and why the evidence supports it." file="/absolute/path/to/file.ts" start=10 end=12 priority=1 confidence=0.87}
```

Keep directives ordered highest priority first. Add a short prose recap only when cross-file context or residual risk would help, and do not duplicate the full finding body there.

Fallback plain-text shape:

```md
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
```

## Comparative ranking / scoring

Use when the task contract asks for blind ranking, comparative scoring, or rubric-driven ordering.

For Codex App rankings where each candidate maps to a real artifact file, you may render one card per ranked item:

```text
::code-comment{title="[Rank 1] Candidate A" body="Top tier. Strongest rubric alignment and fewest contradictions in the bundle." file="/absolute/path/to/candidate-a.md" confidence=0.88}
::code-comment{title="[Rank 2] Candidate B" body="Second tier. Good overall, but weaker on completeness and one rubric dimension." file="/absolute/path/to/candidate-b.md" confidence=0.76}
```

Keep exact rank or tier in the title/body. Use the directive `priority` field only when it honestly represents a coarse tier, not as a fake exact ranking scale.

Fallback plain-text shape:

```md
Ordered Result / Score Table
- 1. [Top tier] Candidate or option, with brief rubric-aligned reason
- 2. [Second tier] Candidate or option, with brief rubric-aligned reason

Evidence / Rationale
- The load-bearing comparisons, contradictions, disqualifiers, or rubric deltas

Uncertainty / Missing Evidence
- Only what limits confidence or blocks a cleaner ranking

Blocked
- Include only when the required bundle is incomplete
```
