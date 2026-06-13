# Portfolio Governance Fixes Design

Date: 2026-06-13

## Purpose

Bring the X-One portfolio documents and repository entry points back in sync with the current product reality after the release push.

The work fixes five portfolio-level issues:

1. Root project matrix and project index are stale.
2. Several READMEs still describe PyPI/Homebrew as future publication even though releases are live.
3. Real-user feedback is still the main maturity gap.
4. Deferred repositories can make the organization look broader than the actual Safe Agent Operations strategy.
5. OPT and self-evolution rules exist, but the feedback/review cadence is not yet visible enough across the portfolio.

## Scope

This is a documentation and governance repair pass. It should not add product code, new runtime behavior, or new standalone product surfaces.

In scope:

- Update the root project matrix and project index to reflect current reality.
- Update README install wording in published repos from future-tense language to current install paths.
- Add or update a portfolio health/governance document that explains feedback loops, deferred-repo handling, and review cadence.
- Strengthen organization-level narrative in `.github` so active tools, data assets, labs, taps, and decision repos are easy to distinguish.
- Add lightweight feedback intake references where they already fit existing project boundaries.

Out of scope:

- Building new features in any tool.
- Reopening deferred products as active tools.
- Creating a hosted dashboard or runtime service.
- Adding heavy automation before the manual governance loop is clear.
- Committing the root-only `x-one-skipped-inputs.md`.

## Repository Plan

### Root X-One Documents

Files:

- `projects.md`
- `final_project_matrix.md`

Changes:

- Mark `mcp-audit`, `agent-pr-evidence`, `agent-failure-packet`, `mcp-risk-index`, and `ai-incident-lab` as released portfolio surfaces.
- Keep `ai-prod-check`, `agent-trace`, and `oss-doctor` as decision repositories, not active products.
- Add clear definitions for:
  - active tool
  - evidence workflow tool
  - data asset
  - lab/content asset
  - decision repository
- Record that PyPI, TestPyPI, GitHub Releases, and Homebrew tap have been verified for the released tools.

### Active Tool READMEs

Repos:

- `agent-pr-evidence`
- `agent-failure-packet`
- `mcp-risk-index`
- `ai-incident-lab`

Changes:

- Replace "after publication" and "after tap update" phrasing with present-tense install instructions.
- Keep English and Simplified Chinese READMEs aligned.
- Keep current limitations visible, especially around real-user tuning and redaction coverage.

### mcp-audit

Changes:

- Preserve its position as the P0 anchor.
- Do not add more rules in this pass.
- Ensure documentation points users toward feedback intake and team adoption rather than another feature list.
- Keep public sample feedback marked as a substitute until real-user feedback exists.

### Deferred Repositories

Repos:

- `ai-prod-check`
- `agent-trace`
- `oss-doctor`

Changes:

- Strengthen first-screen language that these are not active products.
- Make the "absorb / article / watch / reject" path obvious.
- Avoid roadmap language that implies standalone product work is planned.

### Organization Profile

Repo:

- `.github`

Changes:

- Update the organization profile so readers can distinguish released tools from decision repos quickly.
- Link to install surfaces and the portfolio health/governance document.
- Keep the one-line market signal centered on Safe Agent Operations.

### Portfolio Health Document

Preferred location:

- `.github/docs/portfolio-health.md`

Content:

- Current released surfaces.
- Known maturity gaps.
- Feedback intake channels by project.
- Deferred repo handling rules.
- Monthly review checklist.
- Criteria for deleting, absorbing, or reopening a repo.

## Feedback Loop Design

Each active surface should route feedback into one of these categories:

- `false-positive`: finding appears noisy or unsupported.
- `false-negative`: expected risk was missed.
- `adapter-request`: user needs support for a real agent/runtime/config format.
- `scenario-request`: user wants a realistic incident or training scenario.
- `catalog-update`: MCP server facts or evidence need refresh.

The first pass can be documentation-only. Future automation can be added after the manual categories prove useful.

## Verification

Minimum verification:

- Markdown links and headings are coherent.
- English and Simplified Chinese README install sections match semantically.
- `rg "after publication|after tap update"` returns no stale install language in released repos.
- Deferred repos still clearly say they do not ship standalone products.
- All touched repos have clean working trees after commit/push.
- Commits use Conventional/Angular style.
- No direct pushes to `main`; use branches and PRs.

## Risks

- Over-editing could make the portfolio feel more polished than the products are. Mitigation: preserve real limitations.
- Deferred repos could still confuse readers by existing at all. Mitigation: make the first-screen decision language explicit.
- Feedback process could become bureaucracy. Mitigation: keep the first pass lightweight and manual.

## Acceptance Criteria

- A reader can understand the current X-One portfolio in under two minutes.
- Released tools show current install commands, not future publication language.
- Deferred repositories cannot be mistaken for active product builds.
- Real-user feedback is named as the next maturity gate, with clear intake categories.
- The work stays documentation/governance-only unless separately approved.
