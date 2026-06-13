<p align="center">
  <img src="./assets/x-one-avatar.png" width="132" alt="X-One AI avatar">
</p>

<h1 align="center">X-One AI</h1>

<p align="center">
  面向 Safe Agent Operations 的开源工具。
</p>

<p align="center">
  Agentic DevSecOps · MCP safety · AI agent workflow evidence
</p>

<p align="center">
  <a href="./README.md">English</a>
</p>

## 方向

X-One AI 构建的是 AI agents 与真实开发系统之间那一层工程工具。

我们关注：

- MCP tool safety
- agent permissions
- secret 与配置风险
- CI safety gates
- agent-generated PR evidence
- 可调试、可审计的 agent 工作流

## 项目

| 优先级 | 项目 | 作用 |
|---|---|---|
| P0 | [mcp-audit](https://github.com/X-One-AI/mcp-audit) | 扫描 MCP 与 agent 配置中的高风险权限、secret、不安全命令和 CI 安全缺口。 |
| P1 | [agent-pr-evidence](https://github.com/X-One-AI/agent-pr-evidence) | 为 AI agent 生成的 PR 生成可审查的安全与交付证据。 |
| P1 | [agent-failure-packet](https://github.com/X-One-AI/agent-failure-packet) | 为失败 agent run 生成脱敏、可共享的调试包。 |
| P2 | [mcp-risk-index](https://github.com/X-One-AI/mcp-risk-index) | 维护常见 MCP server 与权限风险索引。 |
| P2 | [ai-incident-lab](https://github.com/X-One-AI/ai-incident-lab) | 提供 AI agents、MCP tools 和 agent-generated code 的事故模拟案例。 |

## 当前执行规则

当前只激活 **mcp-audit**。

其它仓库是保留方向，用来沉淀产品判断并避免范围漂移。只有当真实用户反馈指向下一个相邻问题时，才进入主动开发。

## 给 builder 和团队

如果你的团队正在把 AI agents 接入仓库、终端、CI 或 MCP servers，最先要回答的问题很简单：

> 这个 agent 能触碰、执行、泄露或修改什么，而且可能没人注意到？

X-One 的存在，就是为了让这个问题更容易被回答。
