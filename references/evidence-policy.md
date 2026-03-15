# Evidence Policy

Choose evidence based on the claim, not by habit.

## Authority ladder

Use the strongest applicable source in this order:

1. User-provided artifact or baseline
2. Local repo or runtime evidence
3. Primary external sources
4. Secondary external sources as corroboration only

## When to browse

Browse only when at least one of these is true:

- The claim is external to the repo or local artifact.
- The claim is freshness-sensitive.
- The user explicitly asks for verification, citations, or source checking.
- Local evidence is incomplete and an external contract is load-bearing.

Do not browse just because the task uses the word "audit." Purely local or private audits can stay local.

## Citation standard

- External claims: prefer primary sources, capture dates when freshness matters, and cite every nontrivial factual claim.
- Local claims: reference concrete evidence such as file paths, lines, commands, test results, logs, or config values.
- Do not claim reproduction or validation unless tool output supports it.

## Contradictions

- Report the conflict explicitly.
- State which source is stronger and why.
- If you cannot resolve it, leave the claim unresolved and say what would de-risk it.
- Do not smooth over contradictions with a confident summary.

## Report discipline

- Verify load-bearing claims first.
- Mark weakly supported claims as unverified.
- Prefer a short honest report over a longer speculative one.
- Do not invent baselines, deltas, or rollback steps to make the output look complete.
