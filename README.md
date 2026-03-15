# Woz Audit

Skeptical audits for answers, claims, and changes.

`woz-audit` is a Codex skill for reducing decision risk. It helps with fact-checking, artifact review, and change audits by staying evidence-first, surfacing only material issues, and keeping the output easy to act on.

## What it is for

Use `woz-audit` when you want a skeptical pass over something that already exists:

- an answer, memo, plan, or prior model output
- a set of factual claims or citations
- a code change, PR, config, runbook, or operational artifact

The skill is optimized for verification, not generation. It is meant to lower risk before you trust or ship something.

## What it is not for

`woz-audit` is not the right tool for:

- ordinary implementation
- brainstorming
- tone rewrites
- generic summarization
- vague "be careful" requests with nothing concrete to audit

## Audit modes

The skill routes work into one lead mode:

1. Prior-output audit: review an answer, plan, review, memo, or other artifact and verify only the load-bearing claims.
2. Claim verification: determine whether factual claims are verified, contradicted, or still unresolved.
3. System/change audit: inspect code, PRs, configs, logs, migrations, or runbooks for bugs, regressions, unsafe assumptions, or operational risk.

It can also support comparative ranking or scoring tasks, but only by following the task's explicit rubric and output contract rather than forcing everything into a generic audit shape.

## Principles

- Findings first
- Evidence over vibes
- Verify the load-bearing claims, not everything
- Prefer one well-supported material issue over several speculative nits
- Leave uncertainty unresolved when the evidence is weak or conflicting
- Keep output markdown-first, with explicit priority labels and readable structure

## Typical output

The skill usually returns:

- findings ordered by issue priority and decision impact
- the evidence that supports those findings
- assumptions, uncertainty, and blockers when they matter

For ranking work, it leads with the ordered result or score table when the task contract calls for it.

## Example prompts

- `Use $woz-audit to review this answer for material errors and unsupported claims.`
- `Use $woz-audit to fact-check these claims and tell me which are verified, contradicted, or unresolved.`
- `Use $woz-audit to audit this PR for bugs, regressions, and rollback risk.`

## Install

Clone the repo into your Codex skills directory or symlink it there:

```bash
git clone https://github.com/Algorune/woz-audit.git ~/.codex/skills/woz-audit
```

Or, if you keep your skills in a workspace repo:

```bash
ln -s /absolute/path/to/woz-audit ~/.codex/skills/woz-audit
```

## Repo layout

- `SKILL.md`: the skill's operative instructions
- `references/`: focused reference material loaded only when needed
- `agents/openai.yaml`: UI-facing skill metadata

## Read next

Start with [SKILL.md](./SKILL.md) for the actual workflow and rules.
