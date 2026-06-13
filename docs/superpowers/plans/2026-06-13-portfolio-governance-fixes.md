# Portfolio Governance Fixes Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Repair the five portfolio-level issues in X-One documentation and governance so the organization reflects the current released, production-usable Safe Agent Operations portfolio.

**Architecture:** This is a multi-repository documentation/governance change. Each repository gets its own feature branch and PR; the X-One root is not a git repository and must not be initialized. Root-only files are edited in place and intentionally not committed unless the user later creates a root repository.

**Tech Stack:** Markdown, GitHub repositories under `X-One-AI`, `gh` CLI, `rg`, repo-local CI where available.

---

## File Structure

- Root X-One files, not committed:
  - `/Users/moquqicha/Documents/Codes/X-One/projects.md`: current portfolio index.
  - `/Users/moquqicha/Documents/Codes/X-One/final_project_matrix.md`: strategic matrix.
  - `/Users/moquqicha/Documents/Codes/X-One/x-one-skipped-inputs.md`: keep uncommitted status notes only.
- Organization profile repo:
  - `/Users/moquqicha/Documents/Codes/X-One/.github/profile/README.md`: public organization profile.
  - `/Users/moquqicha/Documents/Codes/X-One/.github/profile/README.zh-CN.md`: Chinese organization profile.
  - `/Users/moquqicha/Documents/Codes/X-One/.github/docs/portfolio-health.md`: new portfolio health/governance document.
- Released tool repos:
  - `agent-pr-evidence/README.md`
  - `agent-pr-evidence/README.zh-CN.md`
  - `agent-failure-packet/README.md`
  - `agent-failure-packet/README.zh-CN.md`
  - `mcp-risk-index/README.md`
  - `mcp-risk-index/README.zh-CN.md`
  - `ai-incident-lab/README.md`
  - `ai-incident-lab/README.zh-CN.md`
- P0 anchor repo:
  - `mcp-audit/README.md`
  - `mcp-audit/README.zh-CN.md`
  - `mcp-audit/docs/public-sample-feedback-loop.md`
- Deferred repos:
  - `ai-prod-check/README.md`
  - `ai-prod-check/README.zh-CN.md`
  - `agent-trace/README.md`
  - `agent-trace/README.zh-CN.md`
  - `oss-doctor/README.md`
  - `oss-doctor/README.zh-CN.md`

## Task 1: Update Root Portfolio Documents

**Files:**
- Modify: `/Users/moquqicha/Documents/Codes/X-One/projects.md`
- Modify: `/Users/moquqicha/Documents/Codes/X-One/final_project_matrix.md`
- Do not commit: root is not a git repository.

- [ ] **Step 1: Snapshot current root document language**

Run:

```bash
rg -n "reserved|later|deferred|after|Status|P0|P1|P2|P3|released|Homebrew|PyPI" projects.md final_project_matrix.md
```

Expected: Shows stale language such as P1/P2 projects still marked reserved/later.

- [ ] **Step 2: Rewrite `projects.md` as the current portfolio index**

Required sections:

```markdown
# X-One Project Index

## Portfolio Thesis

X-One builds Safe Agent Operations tools: local-first utilities and evidence assets that help teams adopt AI agents and MCP tools safely in developer workflows.

## Released Tools

| Project | Role | Current Surface | Distribution |
|---|---|---|---|
| `mcp-audit` | P0 config and team policy auditor | CLI, SARIF, team policy gate | PyPI, TestPyPI, Homebrew, GitHub release |
| `agent-pr-evidence` | PR review evidence | CLI, read-only GitHub Action | PyPI, TestPyPI, Homebrew, GitHub release |
| `agent-failure-packet` | Redacted failure evidence | CLI, read-only GitHub Action | PyPI, TestPyPI, Homebrew, GitHub release |
| `mcp-risk-index` | MCP risk data asset | Catalog CLI and evidence-backed entries | PyPI, TestPyPI, Homebrew, GitHub release |
| `ai-incident-lab` | Safe local incident lab | Scenario CLI and bundled scenario pack | PyPI, TestPyPI, Homebrew, GitHub release |

## Decision Repositories

| Project | Decision | Keep Only If |
|---|---|---|
| `ai-prod-check` | Deferred as standalone product | Ideas become concrete checks, articles, or get rejected |
| `agent-trace` | Deferred as tracing platform | Ideas improve `agent-failure-packet` evidence |
| `oss-doctor` | Deferred as generic repo-health tool | Facts support `mcp-risk-index` evidence |

## Next Maturity Gate

The portfolio is released, but maturity now depends on real-user feedback: false positives, false negatives, adapter requests, scenario requests, and catalog updates from actual teams.
```

- [ ] **Step 3: Rewrite `final_project_matrix.md` status language**

Keep the strategic rationale, but update status values:

```text
mcp-audit: released P0 anchor
agent-pr-evidence: released P1 evidence workflow
agent-failure-packet: released P1 evidence workflow
mcp-risk-index: released P2 data asset
ai-incident-lab: released P2 lab/content asset
ai-prod-check: deferred decision repository
agent-trace: deferred decision repository
oss-doctor: deferred decision repository
```

Remove language that says `agent-pr-evidence`, `agent-failure-packet`, `mcp-risk-index`, or `ai-incident-lab` are still only future/later starts.

- [ ] **Step 4: Verify root docs**

Run:

```bash
rg -n "reserved for phase 2|later ecosystem asset|later content|立即做|后续做|主项目验证后做" projects.md final_project_matrix.md
```

Expected: No stale status language for released tools. Deferred language may remain only for decision repositories.

## Task 2: Update Organization Profile and Portfolio Health

**Files:**
- Modify: `/Users/moquqicha/Documents/Codes/X-One/.github/profile/README.md`
- Modify: `/Users/moquqicha/Documents/Codes/X-One/.github/profile/README.zh-CN.md`
- Create: `/Users/moquqicha/Documents/Codes/X-One/.github/docs/portfolio-health.md`

- [ ] **Step 1: Create a branch**

Run:

```bash
cd /Users/moquqicha/Documents/Codes/X-One/.github
git switch main
git pull --ff-only
git switch -c docs/update-portfolio-health
```

Expected: New branch `docs/update-portfolio-health`.

- [ ] **Step 2: Create `docs/portfolio-health.md`**

Include these sections exactly:

```markdown
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
```

- [ ] **Step 3: Update English profile first screen**

Ensure `.github/profile/README.md` says:

```markdown
X-One builds Safe Agent Operations tools for teams adopting AI agents and MCP tools in developer workflows.
```

Add a compact table separating:

```text
Released tools
Data and lab assets
Decision repositories
```

Link to `docs/portfolio-health.md`.

- [ ] **Step 4: Update Chinese profile with the same meaning**

Ensure `.github/profile/README.zh-CN.md` mirrors the English structure and links to `docs/portfolio-health.md`.

- [ ] **Step 5: Verify profile repo**

Run:

```bash
rg -n "Safe Agent Operations|Portfolio Health|Released|Decision|已发布|决策" profile/README.md profile/README.zh-CN.md docs/portfolio-health.md
git diff --check
```

Expected: Matches in all profile docs; `git diff --check` passes.

- [ ] **Step 6: Commit and push**

Run:

```bash
git add profile/README.md profile/README.zh-CN.md docs/portfolio-health.md
git commit -m "docs: update portfolio health"
GIT_SSH_COMMAND='ssh -i ~/.ssh/id_ed25519 -o IdentitiesOnly=yes' git push -u origin docs/update-portfolio-health
gh pr create --repo X-One-AI/.github --base main --head docs/update-portfolio-health --title "docs: update portfolio health" --body "## Summary
- add portfolio health governance
- clarify released tools vs decision repositories
- refresh organization profile entry points

## Verification
- rg portfolio status terms
- git diff --check"
```

## Task 3: Update Released Tool README Install Language

**Files:**
- Modify bilingual READMEs in:
  - `agent-pr-evidence`
  - `agent-failure-packet`
  - `mcp-risk-index`
  - `ai-incident-lab`

- [ ] **Step 1: Create one branch per released tool**

For each repo:

```bash
git switch main
git pull --ff-only
git switch -c docs/update-install-language
```

- [ ] **Step 2: Replace future-tense install headings**

Use this mapping in English READMEs:

```text
From PyPI after publication: -> From PyPI:
From Homebrew after tap update: -> From Homebrew:
After PyPI publication: -> From PyPI:
After Homebrew tap update: -> From Homebrew:
```

Use equivalent Simplified Chinese wording:

```text
从 PyPI 安装：
从 Homebrew 安装：
```

Do not remove limitations or blocked-input sections.

- [ ] **Step 3: Add feedback routing sentence where missing**

Add one short sentence near `Blocked Inputs` or `Current Limits`:

```markdown
Real-user feedback should be classified as false-positive, false-negative, adapter-request, scenario-request, or catalog-update when it applies; portfolio-level handling is tracked in X-One portfolio health docs.
```

Use the matching Chinese meaning in `README.zh-CN.md`.

- [ ] **Step 4: Verify each released tool README**

Run in each repo:

```bash
rg -n "after publication|after tap update|After PyPI publication|After Homebrew tap update" README.md README.zh-CN.md
rg -n "From PyPI:|From Homebrew:|从 PyPI|从 Homebrew" README.md README.zh-CN.md
git diff --check
```

Expected: First command returns no stale future-tense install language. Second command finds current install sections.

- [ ] **Step 5: Commit and PR each repo**

Use:

```bash
git add README.md README.zh-CN.md
git commit -m "docs: update install language"
GIT_SSH_COMMAND='ssh -i ~/.ssh/id_ed25519 -o IdentitiesOnly=yes' git push -u origin docs/update-install-language
gh pr create --repo X-One-AI/<repo> --base main --head docs/update-install-language --title "docs: update install language" --body "## Summary
- replace future-tense install wording with current PyPI/Homebrew install paths
- add feedback routing language
- keep limitations visible

## Verification
- rg stale install wording
- rg current install headings
- git diff --check"
```

## Task 4: Update mcp-audit Feedback and Team Adoption Entry Points

**Files:**
- Modify: `/Users/moquqicha/Documents/Codes/X-One/mcp-audit/README.md`
- Modify: `/Users/moquqicha/Documents/Codes/X-One/mcp-audit/README.zh-CN.md`
- Modify: `/Users/moquqicha/Documents/Codes/X-One/mcp-audit/docs/public-sample-feedback-loop.md`

- [ ] **Step 1: Create branch**

```bash
cd /Users/moquqicha/Documents/Codes/X-One/mcp-audit
git switch main
git pull --ff-only
git switch -c docs/update-feedback-entrypoints
```

- [ ] **Step 2: Add a feedback intake section to README**

Add after team CI guidance:

```markdown
## Feedback Intake

Use public issue templates for false positives and false negatives. Public sample review remains a substitute until 3-5 real users can provide sanitized private scan summaries. Treat feedback as rule input only after it becomes a fixture, documented limitation, or rule-tuning finding.
```

Mirror in Chinese.

- [ ] **Step 3: Tighten public sample substitute wording**

In `docs/public-sample-feedback-loop.md`, make the first paragraph explicit:

```markdown
Public samples are a substitute, not a maturity claim. They keep rule tuning moving while real-user feedback is unavailable.
```

- [ ] **Step 4: Verify**

```bash
rg -n "Feedback Intake|false positives|false negatives|substitute|maturity claim" README.md README.zh-CN.md docs/public-sample-feedback-loop.md
python3 -m pytest tests -q
git diff --check
```

- [ ] **Step 5: Commit and PR**

```bash
git add README.md README.zh-CN.md docs/public-sample-feedback-loop.md
git commit -m "docs: clarify feedback intake"
GIT_SSH_COMMAND='ssh -i ~/.ssh/id_ed25519 -o IdentitiesOnly=yes' git push -u origin docs/update-feedback-entrypoints
gh pr create --repo X-One-AI/mcp-audit --base main --head docs/update-feedback-entrypoints --title "docs: clarify feedback intake" --body "## Summary
- clarify real-user feedback as the next maturity gate
- state that public samples are a substitute, not a maturity claim
- point users to false-positive and false-negative intake

## Verification
- rg feedback language
- python3 -m pytest tests -q
- git diff --check"
```

## Task 5: Strengthen Deferred Repository First Screens

**Files:**
- Modify bilingual READMEs in:
  - `ai-prod-check`
  - `agent-trace`
  - `oss-doctor`

- [ ] **Step 1: Create branch per deferred repo**

```bash
git switch main
git pull --ff-only
git switch -c docs/clarify-deferred-status
```

- [ ] **Step 2: Add first-screen status callout**

Add after language links in each English README:

```markdown
> This is a decision repository, not an active product build. It exists to absorb, reject, or route ideas back into the released Safe Agent Operations tools.
```

Add the matching Chinese sentence in `README.zh-CN.md`.

- [ ] **Step 3: Ensure decision path is visible**

Each README must include one short line near `Decision`:

```markdown
New ideas should be classified as `absorb`, `article`, `watch`, or `reject`.
```

For `agent-trace`, use:

```markdown
New trace ideas should be classified as `move-to-agent-failure-packet`, `watch`, or `reject`.
```

- [ ] **Step 4: Verify**

```bash
rg -n "decision repository|not an active product|absorb|article|watch|reject|move-to-agent-failure-packet|决策仓库|不是活跃产品" README.md README.zh-CN.md
git diff --check
```

- [ ] **Step 5: Commit and PR**

```bash
git add README.md README.zh-CN.md
git commit -m "docs: clarify deferred status"
GIT_SSH_COMMAND='ssh -i ~/.ssh/id_ed25519 -o IdentitiesOnly=yes' git push -u origin docs/clarify-deferred-status
gh pr create --repo X-One-AI/<repo> --base main --head docs/clarify-deferred-status --title "docs: clarify deferred status" --body "## Summary
- clarify this repository is not an active product build
- make routing outcomes visible on the first screen

## Verification
- rg deferred decision language
- git diff --check"
```

## Task 6: Cross-Repo Final Verification and Merge

**Files:**
- No new edits unless verification finds stale language.

- [ ] **Step 1: Check stale install wording across X-One**

```bash
cd /Users/moquqicha/Documents/Codes/X-One
rg -n "after publication|after tap update|After PyPI publication|After Homebrew tap update" \
  agent-pr-evidence agent-failure-packet mcp-risk-index ai-incident-lab
```

Expected: no output.

- [ ] **Step 2: Check deferred repo first screens**

```bash
rg -n "decision repository|not an active product|决策仓库|不是活跃产品" \
  ai-prod-check agent-trace oss-doctor
```

Expected: each deferred repo README pair has explicit status language.

- [ ] **Step 3: Check portfolio health links**

```bash
rg -n "portfolio-health|Portfolio Health|Safe Agent Operations|Released tools|Decision repositories" .github
```

Expected: organization profile links to portfolio health and distinguishes released tools from decision repositories.

- [ ] **Step 4: Check repository states**

```bash
for d in .github mcp-audit agent-pr-evidence agent-failure-packet mcp-risk-index ai-incident-lab ai-prod-check agent-trace oss-doctor; do
  echo "== $d =="
  git -C "$d" status --short --branch
done
```

Expected: touched repos are on their feature branches before merge; after merge and pull, all are `main...origin/main`.

- [ ] **Step 5: Merge PRs after checks pass**

Use `gh pr checks <number> --watch` where CI exists. Merge with squash:

```bash
gh pr merge <number> --repo X-One-AI/<repo> --squash --delete-branch --admin
```

- [ ] **Step 6: Pull merged main branches**

```bash
for d in .github mcp-audit agent-pr-evidence agent-failure-packet mcp-risk-index ai-incident-lab ai-prod-check agent-trace oss-doctor; do
  git -C "$d" switch main
  GIT_SSH_COMMAND='ssh -i ~/.ssh/id_ed25519 -o IdentitiesOnly=yes' git -C "$d" pull --ff-only
done
```

- [ ] **Step 7: Final report**

Report:

- which PRs merged
- which root docs changed but were not committed
- verification commands and outcomes
- whether the five original issues are fixed
