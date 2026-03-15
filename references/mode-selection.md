# Mode Selection

Route the task before you gather evidence.

## Lead modes

### Prior-output audit

Use for an existing answer, plan, review, memo, or document.

- Target: critique the artifact and verify only its load-bearing claims.
- Authority: the artifact first; then local or external evidence for the claims that matter.
- Default shape: Findings, Evidence, Assumptions/Uncertainty, Delta only if a real baseline exists.

### Claim verification

Use for fact-checking, freshness checks, citation review, or source-quality checks.

- Target: determine whether claims are verified, contradicted, or unresolved.
- Authority: primary external sources unless the local artifact is itself the source under review.
- Default shape: Findings, Evidence with dated citations, Unresolved Claims, Confidence/Uncertainty.

### System/change audit

Use for code, PRs, configs, runbooks, logs, migrations, or operational claims.

- Target: identify bugs, regressions, unsafe assumptions, or operational risks.
- Authority: local repo and runtime evidence first; external docs only for external contracts or freshness-sensitive behavior.
- Default shape: Findings, Evidence, Assumptions/Uncertainty, Validation/Rollback only if recommending action.
- Codex App code review variant: when a finding has a precise file location, emit it as a `::code-comment{...}` directive with priority so the app renders it natively.

### Comparative ranking / scoring

This skill is not the lead structure for blind ranking, comparative scoring, or rubric-driven ordering tasks.

- Target: follow the task's rubric and explicit output contract.
- Authority: the provided artifact bundle, rubric, and any local evidence needed to validate the artifacts' claims.
- Default shape: ordered result or score table first when the contract calls for it, then evidence or rationale, then uncertainty or blockers.
- Default posture: borrow this skill's skepticism, evidence discipline, and contradiction handling, but do not force an audit-shaped report when the task is really comparative evaluation.
- This is separate from the normal audit behavior of ordering findings by issue priority inside a single review.

## Routing shortcuts

- Pick one lead mode. Add a secondary mode only for a load-bearing subset.
- Artifact plus factual claims: lead with prior-output audit; verify only the factual subset.
- Code or ops artifact plus vendor behavior: lead with system/change audit; verify only the external contract.
- Comparative ranking or scoring: use the rubric and stated ranking contract as primary; use this skill only as secondary evidence discipline.
- No artifact, claim set, or system to check: this skill probably does not apply.

## Non-goals

Do not use this skill for ordinary implementation, brainstorming, rewriting, summarization, or vague "be careful" prompts with nothing concrete to audit.
