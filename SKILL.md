---
name: woz-audit
description: Route audit/verify/fact-check/review requests into prior-output, claim-verification, or system/change audits. Use for skeptical verification, not ordinary implementation, brainstorming, rewriting, or summarization.
---

# Woz-Audit

Use this skill when the job is to lower decision risk by checking an artifact or claim set, not to generate or rewrite content.

## Default posture

- Preserve the user's stated scope and deliverable.
- Be skeptical without becoming adversarial.
- Optimize for evidence quality and decision risk, not number of findings.
- Prefer one verified material issue over several speculative nits.

## Protocol

1. Lock the target: identify the artifact or claim set, the decision it informs, and any freshness or citation requirement.
2. Route to one lead mode:
   - Prior-output audit: answers, plans, reviews, memos, or docs.
   - Claim verification: factual claims, citations, freshness, or source quality.
   - System/change audit: code, PRs, configs, runbooks, logs, or operational claims.
   Add a secondary mode only for a load-bearing subset.
3. Choose the evidence path from this authority ladder:
   1. User-provided artifact or baseline.
   2. Local repo or runtime evidence for code or system behavior.
   3. Primary external sources for external or freshness-sensitive claims.
   4. Secondary sources only as corroboration.
4. Verify only the load-bearing claims. Browse only if the claim is external, freshness-sensitive, explicitly asks for verification or citations, or depends on an external contract.
5. Reconcile contradictions explicitly. If evidence is weak or conflicting, leave the claim unresolved and say what would de-risk it.
6. Report findings first, ordered by issue priority and decision impact, then evidence, then assumptions or uncertainty. For Codex App code reviews with precise file locations, emit findings as app-native review directives so priorities render natively; keep any prose summary brief and non-duplicative. Otherwise, carry priority explicitly in the lead label of each finding or result row so it stays visible in plain text. Include delta only when a real baseline exists. Include validation or rollback only when recommending changes or addressing an operational decision.
7. If the task is comparative ranking or scoring of candidate artifacts or outputs, use the task's rubric and stated output contract as the lead structure. Present the ordered result or score table first when the contract calls for it, then the supporting evidence and uncertainty. Use this skill only for evidence discipline and contradiction handling, and if the required bundle is incomplete, report the task as blocked instead of fabricating placeholder rankings, scores, or ordered results. This does not change the normal audit behavior of ordering findings by issue priority.

## Report bar

Report a finding only if it has at least one of these:

- concrete user risk or decision impact
- evidence of factual error, contradiction, missing support, regression, or unsafe assumption
- missing evidence that materially blocks confidence

Do not turn style preferences, generic caveats, or speculation into findings unless the user explicitly asked for them.

## When not to use this skill

- ordinary implementation
- brainstorming
- rewriting for tone or clarity
- summarization
- generic "be careful" mode with no artifact, claim set, or system to audit

## References

Open only what you need:

- `references/mode-selection.md`
- `references/evidence-policy.md`
- `references/output-templates.md`

## Hard rules

- Do not silently redefine the task.
- Do not assume the repo is universal SSOT.
- Do not force web research for purely local or private audits.
- Do not invent baselines, deltas, rollback plans, reproduction, or confidence.
- Do not emit app review directives for non-code audits or when you do not have a real file location for the finding.
- Do not confuse prioritizing findings inside an audit with ranking candidate artifacts; finding priority is expected, candidate ranking requires an explicit rubric or output contract.
- If the required evidence bundle is missing, say the task is blocked and name the missing evidence instead of fabricating placeholder rankings, scores, or ordered outputs.
- Do not smooth over contradictions.
- If you notice an out-of-scope concern, record it as a scoped risk or assumption instead of hijacking the task.
- If evidence is insufficient, say the claim is unverified and name the missing evidence.
