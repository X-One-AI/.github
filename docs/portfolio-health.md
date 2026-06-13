# X-One Portfolio Health

## Released Surfaces

| Project | Type | Primary User | Distribution |
|---|---|---|---|
| `mcp-audit` | P0 active tool | teams scanning MCP and agent configs | PyPI, TestPyPI, Homebrew, GitHub release |
| `agent-pr-evidence` | P1 evidence workflow | reviewers of agent-generated PRs | PyPI, TestPyPI, Homebrew, GitHub release |
| `agent-failure-packet` | P1 evidence workflow | maintainers debugging failed agent runs | PyPI, TestPyPI, Homebrew, GitHub release |
| `mcp-risk-index` | P2 data asset | reviewers evaluating MCP servers | PyPI, TestPyPI, Homebrew, GitHub release |
| `ai-incident-lab` | P2 lab/content asset | teams practicing safe agent operations | PyPI, TestPyPI, Homebrew, GitHub release |

## Current Maturity Gap

The portfolio is released, but stable production usefulness now depends on real-user feedback. Public fixtures and public repository samples are useful substitutes, not replacements for users scanning their own configs, PRs, failed runs, and MCP adoption decisions.

## Feedback Categories

- `false-positive`: a finding is noisy, unsupported, or too broad.
- `false-negative`: an expected risk is missed.
- `adapter-request`: a real config, agent runtime, or export format is not supported.
- `scenario-request`: a useful incident or training case is missing.
- `catalog-update`: an MCP server fact, evidence link, or limitation needs refresh.

## Deferred Repository Rules

`ai-prod-check`, `agent-trace`, and `oss-doctor` are decision repositories. They should absorb useful ideas into active tools, convert narrative ideas into articles, watch only evidence-backed candidates, or reject ideas that weaken the Safe Agent Operations signal.

## Monthly Review Checklist

- Review public issues and private feedback notes.
- Promote repeated feedback into fixtures, docs, rules, scenarios, or catalog updates.
- Delete stale ideas that do not support Safe Agent Operations.
- Check README install commands against PyPI and Homebrew.
- Check deferred repositories still read as decision repositories, not active products.
