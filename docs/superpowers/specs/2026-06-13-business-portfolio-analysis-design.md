# X-One Business Portfolio Analysis Design

## Purpose

Analyze every X-One repository as a business asset, not only as a technical artifact. The analysis should help decide which projects deserve continued investment, which should be integrated into stronger projects, which should remain decision repositories, and which should be frozen or deleted.

The primary decision question is:

> Which X-One repositories should continue receiving product investment, and which ones should be merged, watched, frozen, or removed?

## Scope

Analyze these repositories:

- `mcp-audit`
- `agent-pr-evidence`
- `agent-failure-packet`
- `mcp-risk-index`
- `ai-incident-lab`
- `ai-prod-check`
- `agent-trace`
- `oss-doctor`
- `.github` organization profile and portfolio docs
- `homebrew-tap` as distribution infrastructure

The analysis should use current local repository docs and recent merged state as primary context. It should not modify product code or repository docs during the analysis stage.

## Evaluation Framework

Each repository will be evaluated across six business dimensions.

| Dimension | Question |
|---|---|
| User Clarity | Can the target user and buyer be explained in one sentence? |
| Pain Strength | Is this solving a real operational pain, or mostly a conceptual concern? |
| Usage Frequency | Is it a one-time setup tool, recurring workflow tool, periodic governance artifact, or content asset? |
| Differentiation | Does it avoid direct competition with stronger existing platforms? |
| Feedback Potential | Can it generate useful real-user feedback, fixtures, issues, false positives, false negatives, or catalog updates? |
| Mainline Reinforcement | Does it strengthen Safe Agent Operations as a coherent market signal? |

## Verdict Actions

Each repository receives one business verdict.

| Verdict | Meaning |
|---|---|
| Invest | Keep as an independent product and continue maturing it. |
| Integrate | Stop treating it as a standalone product; absorb its useful parts into another X-One project. |
| Watch | Keep as a decision repository; collect evidence only, no product build. |
| Freeze | Stop active work and document why the repo is frozen. |
| Delete | Remove or archive because it weakens the portfolio signal. |

## Per-Repository Output

Each repository analysis should use this structure:

```text
Repo:
- Business verdict:
- Why:
- Main risk:
- Best next business move:
- What not to do:
- Commercial / market-signal implication:
```

The conclusion should be direct. If a repository is weak, the analysis should say so and explain whether the weakness is caused by weak pain, weak distribution, weak differentiation, unclear buyer, or weak fit with the Safe Agent Operations mainline.

## Final Portfolio Matrix

After the per-repository analysis, produce a final matrix with these sections:

```text
Core Bets
Support Assets
Decision Repositories
Candidates To Merge
Candidates To Freeze/Delete
```

The final matrix should make it clear where X-One should spend time next. It should also identify which projects are useful only because they support stronger projects.

## Business Analysis Boundaries

- Do not judge projects only by implementation completeness.
- Do not reward a repo just because it has CI, releases, or packaging.
- Do not assume every repository needs to become a standalone product.
- Do not recommend broad expansion unless it reinforces Safe Agent Operations.
- Do not treat public samples as a substitute for real user demand.
- Do not overfit to open-source stars; focus on target-user pull and portfolio coherence.

## Expected Deliverable

The next artifact should be a written business portfolio analysis, not code changes. It should be suitable for deciding the next project sequence and should include clear, opinionated recommendations.

## Acceptance Criteria

- Every in-scope repository has a business verdict.
- The analysis distinguishes business value from technical readiness.
- The analysis identifies at least one repo that should not receive standalone product investment.
- The final portfolio matrix gives an actionable priority order.
- The report explicitly states what X-One should avoid doing next.
