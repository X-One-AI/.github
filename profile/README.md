<p align="center">
  <img src="./assets/x-one-avatar.png" width="132" alt="X-One AI avatar">
</p>

<h1 align="center">X-One AI</h1>

<p align="center">
  Open-source tools for Safe Agent Operations.
</p>

<p align="center">
  Agentic DevSecOps · MCP safety · AI agent workflow evidence
</p>

<p align="center">
  <a href="./README.zh-CN.md">简体中文</a>
</p>

## Focus

X-One builds Safe Agent Operations tools for teams adopting AI agents and MCP tools in developer workflows.

We care about:

- MCP tool safety
- agent permissions
- secret and configuration risk
- CI safety gates
- agent-generated PR evidence
- debuggable and auditable agent workflows

## Released Tools

| Project | Role | Maturity |
|---|---|---|
| [mcp-audit](https://github.com/X-One-AI/mcp-audit) | Scan MCP and agent configs for risky permissions, secrets, unsafe commands, CI safety gaps, baselines, exceptions, and team policy gates. | Stable production track |
| [agent-pr-evidence](https://github.com/X-One-AI/agent-pr-evidence) | Generate reviewable safety and delivery evidence for AI-agent-generated pull requests. | Released |
| [agent-failure-packet](https://github.com/X-One-AI/agent-failure-packet) | Create redacted, shareable debug packets from failed AI agent runs. | Released |

## Data And Lab Assets

| Project | Role | Maturity |
|---|---|---|
| [mcp-risk-index](https://github.com/X-One-AI/mcp-risk-index) | Maintain an evidence-backed risk index for common MCP servers and permissions. | Released |
| [ai-incident-lab](https://github.com/X-One-AI/ai-incident-lab) | Provide runnable incident simulations for AI agents, MCP tools, and agent-generated code. | Released |
| [homebrew-tap](https://github.com/X-One-AI/homebrew-tap) | Homebrew distribution channel for X-One CLI tools. | Distribution infrastructure |

## Decision Repositories

| Project | Role | Decision Rule |
|---|---|---|
| [ai-prod-check](https://github.com/X-One-AI/ai-prod-check) | Decision repository for production-check ideas. | Absorb, write up, watch, or reject. |
| [agent-trace](https://github.com/X-One-AI/agent-trace) | Decision repository for tracing-platform ideas. | Move useful evidence ideas into `agent-failure-packet`, watch, or reject. |
| [oss-doctor](https://github.com/X-One-AI/oss-doctor) | Decision repository for generic repo-health ideas. | Feed evidence-backed facts into `mcp-risk-index`, watch, or reject. |

Portfolio governance and maturity gates are tracked in [Portfolio Health](../docs/portfolio-health.md).

## Install

```bash
python3 -m pip install xone-mcp-audit
brew tap X-One-AI/tap
brew install x-one-ai/tap/mcp-audit
```

Other released project packages are available through PyPI, TestPyPI, GitHub Releases, and Homebrew formulae.

## Engineering Principles

- Production usable, not demo usable.
- Local-first and reviewable before hosted automation.
- Evidence over vague safety claims.
- Team policy, baselines, exceptions, and release artifacts should be versioned.
- Each project references the shared One Person Team operating model while keeping project-specific constraints and skills.

## For builders and teams

If your team is connecting AI agents to repositories, terminals, CI, or MCP servers, the first useful question is simple:

> What can this agent touch, execute, leak, or change without anyone noticing?

X-One exists to make that question easier to answer.
