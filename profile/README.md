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

## Projects

| Priority | Project | Role |
|---|---|---|
| P0 | [mcp-audit](https://github.com/X-One-AI/mcp-audit) | Scan MCP and agent configs for risky permissions, secrets, unsafe commands, and CI safety gaps. |
| P1 | [agent-pr-evidence](https://github.com/X-One-AI/agent-pr-evidence) | Generate reviewable safety evidence for AI-agent-generated pull requests. |
| P1 | [agent-failure-packet](https://github.com/X-One-AI/agent-failure-packet) | Create redacted, shareable debug packets from failed AI agent runs. |
| P2 | [mcp-risk-index](https://github.com/X-One-AI/mcp-risk-index) | Maintain an open risk index for common MCP servers and permissions. |
| P2 | [ai-incident-lab](https://github.com/X-One-AI/ai-incident-lab) | Provide runnable incident simulations for AI agents, MCP tools, and agent-generated code. |

## Current execution rule

Only **mcp-audit** is active initially.

Other repositories are reserved directions that preserve product decisions and prevent scope creep. They become active only when real user feedback points to the next adjacent problem.

## For builders and teams

If your team is connecting AI agents to repositories, terminals, CI, or MCP servers, the first useful question is simple:

> What can this agent touch, execute, leak, or change without anyone noticing?

X-One exists to make that question easier to answer.
