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

X-One AI builds open-source tools for the engineering layer between AI agents and real developer systems.

We care about:

- MCP tool safety
- agent permissions
- secret and configuration risk
- CI safety gates
- agent-generated PR evidence
- debuggable and auditable agent workflows

## Product Matrix

| Project | Role | Maturity |
|---|---|---|
| [mcp-audit](https://github.com/X-One-AI/mcp-audit) | Scan MCP and agent configs for risky permissions, secrets, unsafe commands, CI safety gaps, baselines, exceptions, and team policy gates. | Stable production track |
| [agent-pr-evidence](https://github.com/X-One-AI/agent-pr-evidence) | Generate reviewable safety and delivery evidence for AI-agent-generated pull requests. | Early production |
| [agent-failure-packet](https://github.com/X-One-AI/agent-failure-packet) | Create redacted, shareable debug packets from failed AI agent runs. | Early production |
| [mcp-risk-index](https://github.com/X-One-AI/mcp-risk-index) | Maintain an evidence-backed risk index for common MCP servers and permissions. | Early production |
| [ai-incident-lab](https://github.com/X-One-AI/ai-incident-lab) | Provide runnable incident simulations for AI agents, MCP tools, and agent-generated code. | Early production |
| [homebrew-tap](https://github.com/X-One-AI/homebrew-tap) | Homebrew distribution channel for X-One CLI tools. | Distribution infrastructure |

## Install

```bash
python3 -m pip install xone-mcp-audit
brew tap X-One-AI/tap
brew install mcp-audit
```

Other project packages are prepared for release through GitHub Actions, PyPI/TestPyPI Trusted Publishing, GitHub Releases, and Homebrew formulae.

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
