# Output Templates

Use the shortest template that still fits the task. Findings come first in every mode.

## Shared rules

- Findings first
- When there are multiple findings, order them by issue priority and decision impact
- Evidence second
- Assumptions or uncertainty third
- Omit sections that do not apply
- Do not emit empty headings or checklist filler
- If the task's explicit contract is comparative ranking or scoring, follow that contract and use these templates only as evidence-discipline guidance
- The anti-fabrication rule for rankings applies to candidate or artifact ordering, not to prioritizing findings within an audit
- If the required evidence bundle is missing, state that the task is blocked instead of inventing placeholder rankings or score tables

## Prior-output audit

Use for answers, plans, memos, reviews, and similar artifacts.

```md
Findings
- Material issue with impact and location

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
- Verified, contradicted, or unresolved claim summaries

Evidence
- Dated citations from primary sources

Unresolved Claims
- Only claims that could not be confirmed

Confidence / Uncertainty
- Residual ambiguity or stale-source risk
```

## System/change audit

Use for code, PRs, configs, runbooks, logs, and operational claims.

```md
Findings
- Material bug, regression, unsafe assumption, or operational risk

Evidence
- Files, tests, logs, repro steps, configs, or command output

Assumptions / Uncertainty
- Missing coverage or unresolved paths

Validation Steps
- Include only when recommending action

Rollback Steps
- Include only when tied to an operational decision or change recommendation
```
